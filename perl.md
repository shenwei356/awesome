# Perl

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [File and Path](#file-and-path)
- [Data structure](#data-structure)
- [Math](#math)
- [System](#system)
- [Language](#language)
- [Misc](#misc)
- [Parallel](#parallel)
- [Performance](#performance)
- [Bio](#bio)
- [Tool](#tool)
- [CPAN](#cpan)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->



## File and Path

- [File::Path](http://perldoc.perl.org/File/Path.htm)
   qw(make\_path remove\_tree) - Create or remove directory trees
- [File::DirWalk](http://perldoc.perl.org/File/DirWalk.htm) Walk through a directory tree and run own code
- [File::Find](http://search.cpan.org/~rjbs/perl-5.18.2/lib/File/Find.pm) - Traverse a directory tree
- [File::Spec](http://perldoc.perl.org/File/Spec.html) - Portably perform operations on file names
- [File::Basename](http://perldoc.perl.org/File/Basename.html) - Parse file paths into directory, filename and suffix.
- [File::Tee](http://search.cpan.org/~salva/File-Tee-0.07/lib/File/Tee.pm) - replicate data sent to a Perl stream
- [File::Copy](http://search.cpan.org/~wolfsage/perl/lib/File/Copy.pm) - Copy files or filehandles
- [Tie::File](http://search.cpan.org/~toddr/Tie-File-1.00/lib/Tie/File.pm) - Access the lines of a disk file via a Perl array

## Data structure

- [Set::IntervalTree](http://search.cpan.org/~benbooth/Set-IntervalTree/lib/Set/IntervalTree.pm) - Perform range-based lookups on sets of ranges。区间树。
- [Set::Bag](http://search.cpan.org/~davido/Set-Bag-1.012/Bag.pm) - bag (multiset) class
- [List::Compare](http://search.cpan.org/~jkeenan/List-Compare-0.39/lib/List/Compare.pm) - Compare elements of two or more lists
- [Array::Diff](http://search.cpan.org/dist/Array-Diff/lib/Array/Diff.pm) - Find the differences between two arrays [attention: sort the array before comparison!!! It's a bug of the module]
- [BerkeleyDB](http://search.cpan.org/dist/BerkeleyDB/BerkeleyDB.pod) - 高效的嵌入式数据库编程库，可以保存任意类型的键/值对，而且可以为一个键保存多个数据。
- [Heap](http://search.cpan.org/dist/Heap/lib/Heap.pm) - Perl extensions for keeping data partially sorted
- [Sort::Fields](http://search.cpan.org/~jnh/Sort-Fields-0.90/Fields.pm) - Sort lines containing delimited fields


## Math

- use [integer](http://perldoc.perl.org/integer.html)
- [Math::Combinatorics](http://search.cpan.org/~allenday/Math-Combinatorics-0.09/lib/Math/Combinatorics.pm) - Perform combinations and permutations on lists

## System

- threads and Thread::Queue，[一个例子](http://www.bioperl.org/wiki/Counting_k-mers_in_large_sets_of_large_sequences#script1)，我的例子[《Using multi threads and message queue to do multi tasks（用多线程和队列来处理多任务）》](http://blog.shenwei.me/using-multi-threads-and-message-queue-to-do-multi-tasks/)

## Language

- [autodie](http://search.cpan.org/~pjf/autodie-2.22/lib/autodie.pm) 和 [Try::Tiny](http://search.cpan.org/~doy/Try-Tiny-0.18/lib/Try/Tiny.pm) 异常处理，[例子](http://www.php-oa.com/2011/05/25/perl-perl-autodie.html)
- [Carp](http://search.cpan.org/~zefram/Carp-1.33/lib/Carp.pm) - alternative warn and die for modules

## Misc

- [Term::ANSIColor](http://perldoc.perl.org/Term/ANSIColor.html) - Color screen output using ANSI escape sequences
- [Number::Bytes::Human](http://search.cpan.org/~dagobert/Number-Bytes-Human/Human.pm) - Convert byte count to human readable format
- [Expect](http://search.cpan.org/~rgiersig/Expect-1.15/Expect.pod) - [使用 Perl 脚本实现交互式命令行程序的管理与测试自动化](http://www.ibm.com/developerworks/cn/linux/l-cn-perl-expect/)

## Parallel

- [Parallel::ForkManage ](http://search.cpan.org/~szabgab/Parallel-ForkManager-1.06/lib/Parallel/ForkManager.pm)- A simple parallel processing fork manager.
- [Parallel::Runner](http://search.cpan.org/~exodist/Parallel-Runner-0.013/lib/Parallel/Runner.pm) - An object to manage running things in parallel processes.
- [MCE](http://search.cpan.org/dist/MCE/) - Many-Core Engine for Perl providing parallel processing capabilities

## Performance

- 内存使用监控Memory Use：[Memory::Usage](http://search.cpan.org/~doneill/Memory-Usage-0.201/lib/Memory/Usage.pm)（[More](http://perlmaven.com/how-much-memory-does-the-perl-application-use)）， Devel::Size， [Devel::SizeMe](http://search.cpan.org/~timb/Devel-SizeMe-0.19/lib/Devel/SizeMe.pm)（More），[Devel::Leak](http://search.cpan.org/~srezic/Devel-Leak/Leak.pm)
- CPU负载信息 [Sys::Info::Device::CPU](http://search.cpan.org/~burak/Sys-Info-Base/lib/Sys/Info/Device/CPU.pm)
- 函数运行时间 [Devel::Profile](http://search.cpan.org/~jaw/Devel-Profile-1.05/Profile.pm)
- [Time::HiRes](http://search.cpan.org/dist/Time-HiRes/HiRes.pm) - High resolution alarm, sleep, gettimeofday, interval timers
- use [Benchmark](http://perldoc.perl.org/Benchmark.html)
- use [Memoize](http://perldoc.perl.org/Memoize.html) - Make functions faster by trading space for time
- [Tips for keeping Perl memory usage low](http://stackoverflow.com/questions/9733146/tips-for-keeping-perl-memory-usage-low)
- [Make your code run faster with Perl's secret turbo module](http://perltricks.com/article/61/2014/1/21/Make-your-code-run-faster-with-Perl-s-secret-turbo-module)


## Bio


- [https://github.com/hyphaltip/genome-scripts](https://github.com/hyphaltip/genome-scripts) Genome Scripts used in fungal comparative genomics


## Tool

- [cpanminus](https://github.com/miyagawa/cpanminus) - get, unpack, build and install modules from CPAN

## CPAN

-  [Put your CPAN distributions on github](http://blogs.perl.org/users/neilb/2014/08/put-your-cpan-distributions-on-github.html)
-  [How to convince Meta CPAN to show a link to the version control system of a distribution?](http://perlmaven.com/how-to-add-link-to-version-control-system-of-a-cpan-distributions)
-  [Dist::Zilla](http://dzil.org/) is a program to make it easier to write, package, manage, and release free software.
