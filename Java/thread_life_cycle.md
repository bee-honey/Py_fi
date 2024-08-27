### ***Thread Life Cycle***

- 0 - New
- 1 - Run
- 2 - Blocked (normally during synchronization)
- 3 - Waiting (for joining)
- 4 - Waiting (specific time/sleep)
- 5 - Terminated


**Join**

  ```java
  Runnable r1 = new Runnable() {
    @Override
    public void run() {
        for(int i = 0; i < 3; i++) {
            System.out.println("R1 : " + i);
        }
    }
  }

  Runnable r2 = new Runnable() {
    @Override
    public void run() {
        for(int i = 0; i < 3; i++) {
            System.out.println("R2 : " + i);
        }
    }
  }

  Thread t1 = new Thread(r1);
  Thread t2 = new Thread(r2);

  t1.start();
  t1.join();
  t2.start();

  /*
  Here the thread t2 will wait until the t1 is completed
  */

  ```


  **Sleep**
  THis would put the thread in a waiting state, but we need to explicitly mention about the sleep duration

  ```java
  Runnable r1 = new Runnable() {
    @Override
    public void run() {
        for(int i = 0; i < 3; i++) {
            System.out.println("R1 : " + i);
        }
    }
  }

  Runnable r2 = new Runnable() {
    @Override
    public void run() {
        for(int i = 0; i < 3; i++) {
            System.out.println("R2 : " + i);
        }
    }
  }

  Thread t1 = new Thread(r1);
  Thread t2 = new Thread(r2);

  t1.start();
  t1.sleep(10000); //10 sec
  t2.start();

  /*
  Here the thread t2 will wait until the t1 is completed
  */

  ```
