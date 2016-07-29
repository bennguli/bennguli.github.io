---
layout: title
posts : Java Android Program to Demonstrate an Advanced Animation Activity
---
This Android Java Program lets you create an Activity to create an Advanced Animation Application.
Here is source code of the Program to create an Activity to Create an Advanced Animation Application. The program is successfully compiled and run on a Windows system using Eclipse Ide. The program output is also shown below.

Using thread and bit-map creating a simple animation of an image.
Main Activity

 package com.example.animation_activity2;
 
 
import android.os.Bundle;
import android.annotation.SuppressLint;
import android.app.Activity;
import android.content.Context;
import android.graphics.Bitmap;
import android.graphics.BitmapFactory;
import android.graphics.Canvas;
import android.view.Menu;
import android.view.MotionEvent;
import android.view.SurfaceHolder;
import android.view.SurfaceView;
import android.view.View;
import android.view.View.OnTouchListener;
 
public class MainActivity extends Activity implements OnTouchListener{
    Ourview v;
    Bitmap bm , bitmap1;
    float x,y;
 
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        // TODO Auto-generated method stub
        super.onCreate(savedInstanceState);
        v = new Ourview(this);
        v.setOnTouchListener(this);
        bm = BitmapFactory.decodeResource(getResources(), R.drawable.image4);
        bitmap1 = BitmapFactory.decodeResource(getResources(), R.drawable.mario2);
 
        x=0;y=0; 
        setContentView(v);
    }
 
    @Override
    protected void onPause() {
        // TODO Auto-generated method stub
        super.onPause();
        v.pause();
    }
 
    @Override
    protected void onResume() {
        // TODO Auto-generated method stub
        super.onResume();
        v.resume();
    }
 
    // surface view is going to be a thread now
    class Ourview extends SurfaceView implements Runnable {
 
        Thread th = null;
        SurfaceHolder holder;
        boolean var = false;
        sprite sprite_object;
        boolean sprite_loaded = false;
        public Ourview(Context context) {
            super(context);
            // TODO Auto-generated constructor stub
            holder = getHolder();
 
 
        }
 
        @Override
        public void run() {
            // TODO Auto-generated method stub
            sprite_object = new sprite(Ourview.this, bitmap1);
            while (var = true) {
                // do stuff
                if (!holder.getSurface().isValid()) {
                    continue;
                }
                if(!sprite_loaded){
                  sprite_loaded=true;
                }
                Canvas c = holder.lockCanvas();// while drawing on a canvas we
                                                // lock it and after drawing on
                                                // it we unlock it
                OnDraw(c);
                holder.unlockCanvasAndPost(c);
            }
        }
 
        @SuppressLint("WrongCall")
        void OnDraw(Canvas c){
            c.drawARGB(255, 250, 150, 20);//rgb values
            c.drawBitmap(bm, x -(bm.getWidth()/2), y -(bm.getHeight()/2), null );
            sprite_object.onDraw(c);
        }
 
        public void pause() {
 
            var = false;
            while (true) {
                try {
                    th.join();// would pause the currently executing thread till
                                // the user finishes its job
                } catch (InterruptedException e) {
                    // TODO Auto-generated catch block
                    e.printStackTrace();
                }
                break;
            }
            th = null;
        }
 
        public void resume() {
            var = true;
            th = new Thread(this);
            th.start();
        }
    }
 
    @Override
    public boolean onTouch(View v, MotionEvent me) {
        // TODO Auto-generated method stub
 
        //x=me.getX();//ontouch listener
        //y=me.getY();
 
        try {
            Thread.sleep(80);
        } catch (InterruptedException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
        switch (me.getAction()) {
        case MotionEvent.ACTION_DOWN:
            x= me.getX();
            y=me.getY();
            break;
 
        case MotionEvent.ACTION_UP:
            x= me.getX();
            y=me.getY();
            break;
 
        case MotionEvent.ACTION_MOVE:
            x= me.getX();
            y=me.getY();
            break;
 
        default:
            break;
        }
 
        return true;
    }
 
 
}
console output
package com.example.animation_activity2;
 
import com.example.animation_activity2.MainActivity.Ourview;
import android.graphics.Bitmap;
import android.graphics.Canvas;
import android.graphics.Rect;
 
public class sprite {
 
    int x,y,xspeed,yspeed,height,width;
    Bitmap b;
    Ourview our_view;
    int current_frame=0,direction=1;
    public sprite(Ourview ourview, Bitmap bitmap1) {
        // TODO Auto-generated constructor stub
        b=bitmap1;
        our_view=ourview;
        //4 rows
        height =b.getHeight()/4;
        //6 columns
        width = b.getWidth()/6;
        x=y=0;
        xspeed=30;
        yspeed=0;
    }
 
    public void onDraw(Canvas c) {
        // TODO Auto-generated method stub
        update();
        int srcX=current_frame*width;
        int srcy=direction*height;
        Rect src = new Rect(srcX, srcy, srcX+width,srcy+ height);
        Rect dst = new Rect(x,y,x+width,y+height); 
        c.drawBitmap(b,src, dst, null);
 
    }
 
    private void update() {
        // TODO Auto-generated method stub
        //1 right
        //3 left
        //down 2
        //up 0
 
        //facing down
        if(x>our_view.getWidth() -width -xspeed){
            xspeed=0;
            yspeed=30;
            direction=2;
        }
 
        //left
        if(y>our_view.getHeight() - height -yspeed){
            xspeed=-30;
            yspeed=0;
            direction=3;
        }
 
        //up
        if(x+xspeed<0){
            x=0;
            xspeed=0;
            yspeed=-30;
            direction=0;
        }
 
        //right
        if(y+yspeed<0){
            y=0;
            xspeed=30;
            yspeed=0;
            direction=1;
        }
        try {
            Thread.sleep(100);
        } catch (InterruptedException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
        current_frame=++current_frame%6;
        x+=xspeed;
        y+=yspeed;
    }
 
}
