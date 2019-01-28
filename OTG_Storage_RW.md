### Android 设备通过OTG线互联读写文件
两个Android设备通过OTG线连接后，作为Host的设备上无法在正常文件系统中显示Client的存储空间。
需要通过android 4.4之后提供的 (SAF)StorageAccessFrameWork 作为接口间接访问。
SAF接口中的DocumentProvider提供各种形式的文件访问接口，也可以通过继承DocumentProvider，实现自定义的
文件访问接口。OTG的外挂接口系统已经给出，USBDocProvider。
SAF将文件系统以树的形式组织起来  Root----Document----[Documents] 并以Uri作为访问地址，不是通常的
filepath 地址，所以在用户选择指定目录之前是无法预知Uri的。

1、Host device DemoApp--DemoActivity 上通过 SAF(StorageAccessFramework) 打开 Select UI。
```
    Intent i = new Intent(Intent.ACTION_OPEN_DOCUMENT_TREE);
    i.setFlags(Intent.FLAG_GRANT_PREFIX_URI_PERMISSION);
    startActivityForResult(i,RESULTCODE);
```

2、在Select UI中选择挂载设备中所需的文件存储目录。

3、 在DemoApp--DemoActivity 的 onActivityResult（int reqCode,int resCode,Intent data）中获得挂载设备的Uri,后续均读写至该Uri。
```
   //设置返回Uri的路径读写权限
   final int takeFlags = data.getFlags() & (Intent.FLAG_GRANT_READ_URI_PERMISSION|
                                         Intent.FLAG_GRANT_WRITE_URI_PERMISSION);
   getContentResolver().takePersistableUriPermission(data.getData(),takeFlags);
   
   //通过DocumentFile创建文件
   DocumentFile file = DocumentFile.fromTreeUri(this,data.getData());
   DocumentFile newfile = file.createFile("video/mp4",currentIndex+".mp4");

```

4、通过ContentResolver向Uri地址写入数据，实现数据的拷贝。
```
   //获取OutPutStream
   OutputStream os = context.getContentResolver().openOutputStream(uri);
   
   //按照正常的文件保存方法向流写入数据
```