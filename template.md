CLOJURE PROGRAMMING LANGUAGE, A LISP LANGUAGE

Clojure is a dynamic, general-purpose and functional Lisp programming language. It combining the approachability and interactive development of a scripting language with an efficient and robust infrastructure for multithreaded programming. Clojure released in 2007 by Rich Hickey. Rich Hickey is a prolific speaker and has a lot of ideas about programming.

It runs in the JVM (Java Virtual Machine), CLR (Common Language Runtime) and JavaScript platforms. It influenced these programming languages. Also the name Clojure was created inspired by C #, Lisp and Java programming languages (C, L, and J). Clojure is a modern Lisp for functional programming. And it is designed for symbiotic and concurrency with the built-in Java platform.

So why should we use Clojure programming language? First, The Clojure has a very plain and simple structure and the syntax is also very plain. For example, adding the number 2 and 3 in the language is so simple like that: (+ 2 3) => 5. Another reason for using the language is Java Interoperability. That is, since it written on JVM, Clojure gives access to all available Java (or any JVM language) libraries and their frameworks. So you can call Java code from Clojure code, or vice versa. Another point of the Clojure language is that it is designed in accordance with the REPL principle. REPL (Read Eval Print Loop) is a very important for Lisp programmers. It is a tool that you communicate instantly with the program you wrote in an interactive way and evolve it. And REPL allows you to run any language and any code within the Clojure language. The macro system of Lisp provides you an opportunity to extend the language. Thus, you can get rid of duplicate codes you don’t want by writing nice macros. Compared to mutable languages, Clojure is a good programming language for concurrency programming. One of the reasons for using Clojure is that its simultaneous programs are designed to be easy, fun and at the same time with much less error rate. Moreover, the language has 4 mutable reference types and this facilitates our work on state management issues. These are Var, Atom, Agent, and Ref. 

In Clojure, immutability eliminates most of the problem, then it shares freely between threads. It is multi-core technology of Clojure. Clojure seperates multimethods polymorphism from OO and types and it supports multiple taxonomies. So, these reasons prove that polymorphism is good for Clojure and other Lisp languages. 

Clojure provides command line tools that can be used to start a Clojure REPL. Clojure requires Java and you can use any Java Installation like commercial release from Oracle or an open source version based on OpenJDK (like adoptopenjdk). Clojure is compatible with major operating systems such as Mac, Linux, Windows for installation and it is simple to install. Clojure is installed via Homebrew in Mac platform. Install the command line tools with brew from the Clojure: “brew install clojure/tools/clojure”. If you have already installed it, then you can upgrade to the latest version with: “brew upgrade clojure/tools/clojure”. Installation on Linux is similar to the Mac installation with Homebrew on Linux. Make sure the bash, curl, rlwrap, and Java dependencies are installed. Browser-based options such as ‘local build’ and ‘Clojure online’ are also available to run Clojure.

Some general codes to understand the language and some interesting and special codes for the language are given below.

--> Hello, World!  user=> (println "Hello, world!")

--> Modulo  user=>  (mod 3 2)   = 1

--> Power  user=>  (power 2 3) = 8

--> Bigint  user=> (+ (bigint Long/MAX_VALUE) 10) =  9223372036854775817N


--> Fibonacci-Recur  user=> (defn fibo-recursive [n]
         (if (or (= n 0) (= n 1))
           n
           (+ (fibo-recursive (- n 1)) (fibo-recursive (- n 2)))))
user=> (fibo-recursive 6) = 8     
Loop  user> (defn count-up [max]
        (loop [count 0]
          (if (= count max)
            (println "Done!")
            (do
              (println (str "Counting " count))
              (recur (inc count))))))
user> (count-up 5)
Counting 0
Counting 1
Counting 2
Counting 3
Counting 4
Done!
Nil


--> A code ‘Bob’ from exercism.io  
(ns bob
  (:require [clojure.string :as str]))

(defn- has-letters? [s] (re-seq #"[a-zA-Z]" s))
(defn- question? [s] (and (= \? (last (str/trim s)))))
(defn- shouting? [s] (and (has-letters? s) (= s (str/upper-case s))))
(defn- shouting-question? [s] (and (question? s) (shouting? s)))
 (defn response-for [s]
  (cond
    (clojure.string/blank? s) "Fine. Be that way!"
    (shouting-question? s) "Calm down, I know what I'm doing!"
    (shouting? s) "Whoa, chill out!"
    (question? s) "Sure." :
     else "Whatever."))

