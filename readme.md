# Summary

AsyncTaskTest is a library to easier the process of testing AsyncTask classes.
There are multiple ways to test AsyncTask, but most of them are complex or relies on changing class structure.
AsyncTaskTest was made to be easy to use without any modification on your class, you just use it on your jUnit tests.


# Installation

I'm working to put it on gradle, until, just copy the files AsyncTaskTest and AsyncTest to your project.

# Usage

To use it, call method build passing the instance of your AsyncTask class, in sequence call run, passing an anonymous interface implementing the method test. This method receives a parameter which will be the result of the AsyncTask when its done. Cast it to the apropriated class and assert this result.

Example:
```java
  // Example of async class:
  public MyClassWithAsyncTask extends AsyncTask<String, Void, Integer>{
  	// ... implementation
  }
	
	
  // On your test file:
  // For better understanding I will omit some parts with ...
  public void makeGETRequest(){
		...
		myAsyncTaskInstance.execute(...);
		AsyncTaskTest.build(myAsyncTaskInstance).
                    run(new AsyncTest() {
                        @Override
                        public void test(Object result) {
                            Assert.assertEquals(200, (Integer)result);
                        }
                    });
		
  }
``

# License

MIT

# Author

Leonardo Soares e Silva <lsoaresesilva@gmail.com>






 