## 1. 功能说明
可接入三维页面查看模型
使用的ip端口为:
`http://192.168.177.20:8989`

## 2. 接入流程说明
### aar包导入
`sdk_guoneng-release` 放入 `libs` 文件夹中
模块的 `build.gradle` 添加 
```
dependencies {
	....
	 implementation fileTree(dir: 'libs', include: ['*.aar'])
}
```

### 代码接入
1. 在自定义Application类中添加初始化方法
```
public class App extends Application {
    @Override
    public void onCreate() {
        super.onCreate();
        RzonSDK.INSTANCE.initialize(this);
    }
}
```
2. 在需要跳转显示三维页面的地方添加方法
`RzonSDK.INSTANCE.enter(context);`
如下
```
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        findViewById(R.id.button).setOnClickListener(view -> {
            RzonSDK.INSTANCE.enter(this);
        });
    }
}
```
