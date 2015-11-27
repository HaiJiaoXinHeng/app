常见Android开发控件
===================================
Android开发中遇到了一些特殊需求，在此罗列自己收集总结到的控件或者方法，在此分享！
-------------------------------------------------------------------------
使用方法是:把library作为库引入

####一、沉浸式状态栏
  1、布局文件中的title控件中添加android:clipToPadding="true" android:fitsSystemWindows="true"       
  2、在布局文件中的title种添加paddingTop="paddingTop",SDK19以上padding20dp,19一下为0dp      
  2、在onCreat中调用：SystemBarTintManager.initSystemBar(this,R.color.colorAccent);

####二、右滑退出
  1、需要右滑退出的activity集成SwipeBackActivity,默认右滑退出;      
  2、可以设置setDragEdge(TOP,...)的方法,设置其他方向退出
  
####三、工具类方法介绍
  FileUtils文件相关操作类:
     writeFile(InputStream is, String path, boolean recreate) 把流写入文件;       
     writeFile(byte[] content, String path, boolean append)把字符数组写入文件;       
     writeFile(String content, String path, boolean append)把字符串写入文件;        
     writeProperties(String filePath, String key, String value, String comment)把键值对写入文件;        
     copy(String src, String des, boolean delete)复制文件或更改名称      
  LogUtils日志打印工具类       
  StringUtils字符串操作类     
  UIUtils关于UI界面的操作类
  ToastUtils是吐丝的单例操作        
  DisplayUtil是dppxsp之间的相互转换工具类
   
####四、下拉刷新上拉加载  

    PullToRefresh包:
    
    1,布局文件
    
        *<com.limxing.library.PullToRefresh.SwipeRefreshLayout
         android:id="@+id/main_fresh"
         android:layout_width="match_parent"
         android:layout_height="match_parent"
         android:layout_below="@+id/main_title"
         swiperefresh:srlAnimationStyle="rotate"
         swiperefresh:srlTextSize="16sp" >
        
         <ListView
         android:id="@+id/main_listview"
         android:layout_width="match_parent"
         android:layout_height="match_parent"
         android:background="#ffffff"
         android:dividerHeight="1dp" >
         </ListView>
         </com.limxing.library.PullToRefresh.SwipeRefreshLayout>*
    2,在activity中获取到两个控件,SwipeRefreshLayout控件需要设置监听:     
        
        *main_fresh.setOnRefreshListener(this);
         main_fresh.setOnLoadListener(this);*
         在监听方法中实现响应的操作
    3,调用方法刷新加载完成恢复:     
        
  




