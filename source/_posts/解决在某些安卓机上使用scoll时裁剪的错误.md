title: 解决在某些安卓机上使用scoll时裁剪的错误
date: 2015-05-25 11:52:28
tags: android
auth: ATJZ
---
一些安卓机在使用了scroll、controlswitch等其他使用了裁剪的控件时，会出现控件失效的情况，可以在appActivity.java中重写onCreateView()函数来完成修复

	import org.cocos2dx.lib.Cocos2dxGLSurfaceView;
	public class AppActivity extends Cocos2dxActivity {
		public Cocos2dxGLSurfaceView onCreateView() {  
		       Cocos2dxGLSurfaceView glSurfaceView = new Cocos2dxGLSurfaceView(this);  
		       // TestCpp should create stencil buffer  
		       glSurfaceView.setEGLConfigChooser(5, 6, 5, 0, 16, 8);  			         
		       return glSurfaceView;  
		}
	} 
