# 统一日志模块

根据不同的buildType，对日志进行不同处理。错误日志可以通过注入的接口，自定义处理，比如上传到监控平台等。
支持获取当前日志的行数，支持当前日志的堆栈信息。

## LogUtils的使用

#### 1、aar已上传Jcenter，只要如下gradle依赖即可

    compile 'com.showjoy.android:log:1.0.0'
    
#### 2、首先在application的onCreate里调用init

    public class MainApplication extends Application {
        @Override
        public void onCreate() {
           super.onCreate();

           SHLog.TAG = "What you like";
           SHLog.LOG_DEBUG = BuildConfig.DEBUG;

           //错误日志监控
           SHLog.setErrorListener(...);
           //一般日志监控
           SHLog.setLogListener(...);
        }
    }


​
