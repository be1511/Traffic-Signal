# Traffic-Signal
Code :<br />
import java.awt.*;<br />
import java.applet.*;<br />
import java.awt.event.*;<br />
public class traffic extends Applet implements Runnable<br />
{<br />
Thread t;<br />
Font f,f1;<br />
int i=0,a=0,j=0;<br />
public void init(){</p>
<p>	setBackground(Color.lightGray);</p>
<p>f=new Font(“TimesNewRoman”,f.ITALIC,28);<br />
f1=new Font(“TimesNewRoman”,Font.ITALIC+Font.BOLD,28);</p>
<p>}<br />
public void start()<br />
{<br />
t=new Thread(this);<br />
t.start();<br />
}</p>
<p>public void run()<br />
{</p>
<p>for(i=25;i>=0;i–)//countdown<br />
{</p>
<p>try<br />
{<br />
Thread.sleep(1000);<br />
}<br />
catch(Exception e)<br />
{<br />
System.out.println(e);<br />
}<br />
if(i<=25 && i>3)//red<br />
{<br />
	a=1;<br />
	repaint();<br />
}<br />
else<br />
if(i<=3 && i>0)//yelloe<br />
{<br />
	a=2;<br />
	repaint();<br />
}<br />
else<br />
if(i==0)//green<br />
{</p>
<p>	for(j=0;j<25;j++)<br />
{<br />
	a=3;<br />
	try<br />
	{<br />
		Thread.sleep(1000);<br />
	}<br />
	catch(Exception e)<br />
	{<br />
		System.out.println(e);<br />
	}</p>
<p>	repaint();</p>
<p>}</p>
<p>         if(j==25)//end of green(return to red)<br />
			 {<br />
				 run();<br />
			 }</p>
<p>}</p>
<p>}</p>
<p>repaint();<br />
}</p>
<p>public void paint(Graphics g)<br />
{<br />
setBackground(Color.lightGray);//ROAD</p>
<p>g.setColor(Color.black);//pole top<br />
g.fillArc(100,150,100,100,0,180);<br />
g.drawArc(100,150,100,100,0,180);</p>
<p>g.setColor(Color.black);//POLE UP<br />
g.fillRect(150,150,50,150);<br />
g.drawRect(150,150,50,150);</p>
<p>g.setColor(Color.black);//POLE DOWN<br />
g.fillRect(165,300,20,155);<br />
g.drawRect(165,300,20,155);</p>
<p>g.drawOval(150,150,50,50);//RED</p>
<p>g.drawOval(150,200,50,50);//YELLOW</p>
<p>g.drawOval(150,250,50,50);//GREEN</p>
<p>g.setColor(Color.red);//COUNTDOWN STOP<br />
g.setFont(f);<br />
g.drawString(“”+i,50,50);</p>
<p>g.setColor(Color.white);//CROSSING1<br />
g.fillRect(300,5,15,125);<br />
g.drawRect(300,5,15,125);</p>
<p>g.setColor(Color.white);<br />
g.fillRect(300,145,15,135);<br />
g.drawRect(300,145,15,135);</p>
<p>g.setColor(Color.white);<br />
g.fillRect(300,300,15,135);<br />
g.drawRect(300,300,15,135);</p>
<p>g.setColor(Color.white);//CROSSING2<br />
g.fillRect(450,5,15,125);<br />
g.drawRect(450,5,15,125);</p>
<p>g.setColor(Color.white);<br />
g.fillRect(450,145,15,135);<br />
g.drawRect(450,145,15,135);</p>
<p>g.setColor(Color.white);<br />
g.fillRect(450,300,15,135);<br />
g.drawRect(450,300,15,135);</p>
<p>g.setColor(Color.black);//TREE1DOWN<br />
g.fillRect(600,300,15,135);<br />
g.drawRect(600,300,15,135);</p>
<p>g.setColor(Color.green);//TREE1UP<br />
g.fillArc(560,290,100,100,0,180);<br />
g.drawArc(560,290,100,100,0,180);</p>
<p>g.setColor(Color.black);//TREE2DOWN<br />
g.fillRect(460,300,15,135);<br />
g.drawRect(460,300,15,135);</p>
<p>g.setColor(Color.green);//TREE2UP<br />
g.fillArc(420,290,100,100,0,180);<br />
g.drawArc(420,290,100,100,0,180);</p>
<p>if(a==1)//REDSIGNAL<br />
{<br />
	g.setColor(Color.red);<br />
	g.fillOval(150,150,50,50);<br />
	g.drawOval(150,150,50,50);<br />
	g.drawString(“STOP”,50,150);<br />
}<br />
if(a==2)//YELLOWSIGNAL<br />
{<br />
	g.setColor(Color.yellow);<br />
	g.fillOval(150,200,50,50);<br />
	g.drawOval(150,200,50,50);<br />
	g.drawString(“READY”,50,200);<br />
}<br />
if(a==3)//GREENSIGNAL<br />
{<br />
	g.setColor(Color.blue);//countdown<br />
	g.setFont(f);<br />
g.drawString(“”+j,150,50);</p>
<p>	g.setColor(Color.green);<br />
	g.fillOval(150,250,50,50);<br />
	g.drawOval(150,250,50,50);<br />
	g.drawString(“GO”,50,250);</p>
<p>}</p>
<p>int x1[]={220,300,300,280};<br />
	int y1[]={250,150,250,150};<br />
	int n1=4;<br />
	int n2=3;<br />
	int x2[]={340,380,380};<br />
	int y2[]={150,100,150};</p>
<p>	int x3[]={460,460,500};<br />
	int y3[]={150,100,150};</p>
<p>g.setColor(Color.black);<br />
	g.fillPolygon(x1,y1,n1);<br />
g.drawPolygon(x1,y1,n1);</p>
<p>	g.setColor(Color.yellow);<br />
	g.fillRect(380,100,80,50);<br />
g.drawRect(380,100,80,50);</p>
<p>g.setColor(Color.yellow);<br />
	g.fillPolygon(x2,y2,n2);<br />
g.drawPolygon(x2,y2,n2);</p>
<p>g.setColor(Color.yellow);<br />
	g.fillPolygon(x3,y3,n2);<br />
g.drawPolygon(x3,y3,n2);</p>
<p>g.setColor(Color.black);<br />
	g.fillOval(440,210,60,60);<br />
g.drawOval(440,210,60,60);</p>
<p>g.setColor(Color.black);<br />
	g.fillOval(340,210,60,60);<br />
g.drawOval(340,210,60,60);</p>
<p>g.setColor(Color.red);<br />
	g.fillRect(300,150,250,100);<br />
g.drawRect(300,150,250,100);</p>
<p>g.setColor(Color.black);<br />
g.setFont(f1);<br />
g.drawString (“Zumbo”,380,200);</p>
<p>}<br />
}</p>
<p>
