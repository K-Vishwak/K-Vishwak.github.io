---
title: "how much do you debug javascript?"
datePublished: Thu Feb 17 2022 08:35:07 GMT+0000 (Coordinated Universal Time)
cuid: ckzqq9q9c0pk5r4s1bon70e01
slug: how-much-do-you-debug-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/unsplash/HsTnjCVQ798/upload/v1645087074007/QiTI7SI-x.jpeg
tags: javascript, languages, hashnode, 2articles1week

---

`Debugging` - The process of identifying errors in programming code is called debugging.

Debugging is inevitable when you start writing the code. It is the very much next act for the line of code you write.

Until you get the expected behavior what you are actually doing is coding & debugging. Hence knowing different debugging techniques is very much important.

Javascript is the underlying language for all front-end libraries and knowing how to debug is very much useful.

There are three main types of errors that occur while coding in javascript. Those are:

**Syntax Errors:** These are the mistakes in source code like spelling mistakes, punctuations, incorrect labels, which can cause error messages generated at compile time.

Most of these are visible in your IDE and we can easily correct and resolve them.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645071458257/BeTyDhDW0.png align="left")

**Runtime Errors:** Occurs during the runtime of the program after being interpreted by the compiler.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645071270327/NWrlnKDk2.png align="left")

Before compilation, there is no error but while running it has thrown an error.

**Logical Errors:** Program executes successfully but generates unintended results.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645071211473/WN-kbS514.png align="left")

You intended to compare but you assigned. Hence `first` became 20.

Ok.

Without the knowledge of errors, there is no point in discussing debugging. Hence that part is over and let's start debugging now.

Syntax errors can be resolved upfront as such no techniques are needed. Run-time errors are usually logged in `browser console` with very much possible stack trace and can be resolved easily.

The tricky part is logical errors where we are really required to apply debugging techniques.

### 1\. console.log

The primary technique is to log the result of your logic to see whether the result is intended or not. This will log to your browser console.

Follow the below steps to open the browser developer tools (which includes console) in the browser:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645169988683/f_Oongicb.png align="left")

example:

```bash
<html>

<body>
    <p id="arr">
    </p>
    <script>
        const arr = [1, 2, 3, 4, 5];
        arr.push(6);

        // Print in console to validate.
        console.log(arr);
        document.getElementById('arr').innerHTML = arr;
    </script>
</body>

</html>
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645079633459/knklalm26.png align="left")

The above one is a simple example though whenever you see that your result is not intended you can log and verify in the same way. *Ensure to remove console log statements once you resolve the issue from code.*

### 2\. debugger;

It is a keyword that is used to stop the execution of javascript and calls the debugging function. You can use browser debugging options to validate the result. This also works only when you restart the application by opening browser developer tools.

```bash
<html>

<body>
    <p id="arr">
    </p>
    <script>
        const arr = [1, 2, 3, 4, 5];
        arr.push(6);

        // stops execution at below line.
        debugger;
        document.getElementById('arr').innerHTML = arr;
    </script>
</body>

</html>
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645079969830/LMkh9iZGc.png align="left")

### 3\. Browser Debugging Options

Same as debugger;, browser breakpoint also stops execution and lets you walk through each line of code to validate the result.

Open developer tools -&gt; Navigate to sources -&gt; Click on left nav on line numbers to add breakpoint -&gt; reload the application

![test.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645082552200/p5LYea_Bc.png align="left")

### 4\. Use `Sources` tab

There might be situations where you want to verify some code snippet even while debugging the main application code.

![first.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645085385254/sQ7Cpx2PY.png align="left")

Open developer options -&gt; Go to Sources tab -&gt; Click on New Snippet in left nav -&gt; new file added in mid pannel -&gt; write another program -&gt; Click enter to run program.

![second.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645085365523/nVXDxw4uq.png align="left")

### 5\. Device Mode in browser

You can also verify how your UI looks in different devices in UI. Not technically a debugging code but if you are setting elements based on the resolution using javascript then you can use this feature.

Open developer tools -&gt; Click on the 'Toggle Device Toolbar' option (shown in below screenshot) -&gt; Your application is shown in device -&gt; You can also switch to different devices using the top dropdown.

![third.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645087020548/UacS9-5zw.png align="left")

### 6\. Watch Expressions feature

Watch expression feature in browser developer tools used to instantly validate the JS expression result over time while debugging the code.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645086444105/Nyk7acDYA.png align="left")

\`

See the `arr` values at `breakpoint#8` and `breakpoint#9`. Over the period `arr` has been updated.

This watch expression is handier when you are dealing with complex logic.

### 7\. Event Listener Breakpoints

Just below of watch expressions feature there is `Event Listener Breakpoints` there you can have many actions to use as breakpoints.

Open `Mouse` triangle and check the 'click\` event which lets you stop execution on click.

Not just mouse events, every other interaction with the application is listed there. We can use any event as a breakpoint.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645168716920/O1g1h80aE.png align="left")

### 8\. Use `Debug` from console

Manually type `debug(function_name)` in the console which lets you stop execution wherever the function executes.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645169507948/NvAVoQcxz.png align="left")

Reload the page and observe that execution stopped at the mentioned function.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1645169626590/Cyb0RXVOn.png align="left")

Thank you :) Happy reading!E