package marchthird;

import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

class runnableexp implements Runnable
{
public void run()
{
	System.out.println("run() from a different thread than main");

}
}
public class threads {
static ExecutorService executor=Executors.newFixedThreadPool(2);
public static void main(String[] args) {
	runnableexp r1=new runnableexp();
	Thread t1=new Thread(r1);
	t1.start();
	executor.submit(r1);
	executor.shutdown();
	
}
}
