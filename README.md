goid
====

Get goroutine ID

http://wendal.net/2013/0205.html

example
====
    // goid
    package main
    
    import (
    	"fmt"
    	"time"
    	"github.com/axgle/goid"
    )
    
    func main() {
    	fmt.Println(goid.Get(), "main 1")
    	for i := 1; i < 10; i++ {
    
    		go func(i int) {
    			fmt.Println(goid.Get(), i)
    		}(i)
    	}
    	fmt.Println(goid.Get(), "main 2")
    	time.Sleep(time.Second)
    }
