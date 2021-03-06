# *Perl* version of the *Atlas* toolkit

[![Run on Repl.it](https://q37.info/s/kpm7xhfm.png)](https://q37.info/s/h3h34zgq)  [![About online demonstrations](https://img.shields.io/badge/about-online%20demonstrations-informational)](https://q37.info/s/sssznrb4)

[![Version 0.12](https://img.shields.io/static/v1.svg?&color=90b4ed&label=Version&message=0.12&style=for-the-badge)](http://github.com/epeios-q37/atlas-perl/)
[![license: MIT](https://img.shields.io/github/license/epeios-q37/atlas-perl?color=yellow&style=for-the-badge)](https://github.com/epeios-q37/atlas-perl/blob/master/LICENSE)
[![Documentation](https://img.shields.io/static/v1?label=documentation&message=atlastk.org&color=ff69b4&style=for-the-badge)](https://atlastk.org)  



> The [*Atlas* toolkit](https://atlastk.org) is available for:
> 
> | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Language | *GitHub* repository | Online démonstrations
> |-|-|-|:-:|
> | ![Java](https://q37.info/s/sgb9nq7x.svg) | [*Java*](https://q37.info/s/qtnkp9w4)  |<https://github.com/epeios-q37/atlas-java> | [![Run on Replit](https://q37.info/s/kpm7xhfm.png)](https://q37.info/s/3vwk3h3n) |
> | ![Node.js](https://q37.info/s/b9ctj4bb.svg) | [*Node.js*](https://q37.info/s/3d7hr733) | <https://github.com/epeios-q37/atlas-node> | [![Run on Replit](https://q37.info/s/kpm7xhfm.png)](https://q37.info/s/st7gccd4) |
> | ![Perl](https://q37.info/s/v9qkzvhk.svg) | [*Perl*](https://q37.info/s/4nvmwjgg)  |<https://github.com/epeios-q37/atlas-perl> | [![Run on Replit](https://q37.info/s/kpm7xhfm.png)](https://q37.info/s/h3h34zgq) |
> | ![Python](https://q37.info/s/t4s3p4rk.svg) | [*Python*](https://q37.info/s/pd7j9k4r)  | <https://github.com/epeios-q37/atlas-python> | [![Run on Replit](https://q37.info/s/kpm7xhfm.png)](https://q37.info/s/vwpsw73v) |
> | ![Ruby](https://q37.info/s/ngxztq4t.svg) | [*Ruby*](https://q37.info/s/gkfj3zpz)  | <https://github.com/epeios-q37/atlas-ruby> | [![Run on Replit](https://q37.info/s/kpm7xhfm.png)](https://q37.info/s/9thdtmjg) |




---

## Straight to the point: the ["Hello, World!"](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program) program

### Source code

```perl
use Atlas;

my $body = '
<fieldset>
 <input id="input" maxlength="20" placeholder="Enter a name here" type="text"
         data-xdh-onevent="Submit" value="World"/>
 <div style="display: flex; justify-content: space-around; margin: 5px auto auto auto;">
  <button data-xdh-onevent="Submit">Submit</button>
  <button data-xdh-onevent="Clear">Clear</button>
 </div>
</fieldset>
';

sub acConnect {
 my ($hello, $dom) = @_;

 $dom->inner("",$body);
 $dom->focus("input");
}

sub acSubmit {
 my ($hello, $dom) = @_;

 $dom->alert("Hello, " . $dom->getContent("input") . "!");
 $dom->focus("input");
}

sub acClear {
 my ($hello, $dom) = @_;

 if ( $dom->confirm("Are you sure?") ) {
  $dom->setContent("input", "");
 }

 $dom->focus("input");
}

my %callbacks = (
 "" => \&acConnect,
 "Submit" => \&acSubmit,
 "Clear" => \&acClear,
);

Atlas::launch(\%callbacks);
```

### Result

[![Little demonstration](https://q37.info/download/assets/Hello.gif "A basic example")](https://q37.info/s/h3h34zgq)

### See for yourself right now - it's quick and easy!

#### Online, with nothing to install [![About online demonstrations](https://img.shields.io/badge/about-online%20demonstrations-informational)](https://q37.info/s/sssznrb4)

Thanks to [*Replit*](https://q37.info/s/mxmgq3qm), an [online IDE](https://q37.info/s/zzkzbdw7), you can write and run programs using the *Atlas* toolkit directly in your web browser, without having to install *Perl* on your computer.

To see some examples, like the following [*TodoMVC*](http://todomvc.com/) application or the above ["Hello, World!"](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program) program, simply:
- go [here](https://q37.info/s/h3h34zgq) (also accessible with the [![Run on Repl.it](https://q37.info/s/kpm7xhfm.png)](https://q37.info/s/h3h34zgq) badge at the top of this page),
-  click on the green `run` button,
-  choose the demonstration to launch,
-  open the then displayed URL in a browser (should be clickable), 
- … and, as you wish, run your own tests directly in your browser, by modifying the code of the examples or by writing your own code.

[![TodoMVC](https://q37.info/download/TodoMVC.gif "The TodoMVC application made with the Atlas toolkit")](https://q37.info/s/h3h34zgq)

#### With *Perl* on your computer

```
git clone https://github.com/epeios-q37/atlas-perl
cd atlas-perl/examples
perl -I ../atlastk Hello/Hello.pl
```

## Your turn

If you want to take your code to the next level, from [CLI](https://q37.info/s/cnh9nrw9) to [GUI](https://q37.info/s/hw9n3pjs), then you found the right toolkit.

With the [*Atlas* toolkit](http://atlastk.org/), you transform your programs in modern web applications ([*SPA*](https://q37.info/s/7sbmxd3j)), but without the usual hassles:
- no *JavaScript* to write; only *HTML*(/*CSS*) and *Perl*,
- no [front and back end architecture](https://q37.info/s/px7hhztd) to bother with,
- no [web server](https://q37.info/s/n3hpwsht) (*Apache*, *Nginx*…) to install,
- no need to deploy your application on a remote server,
- no incoming port to open on your internet box or routeur.

The *Atlas* toolkit is written in pure *Perl*, with no native code and no dependencies, allowing the *Atlas* toolkit to be used on all environments where *Perl* is available. 

And, icing on the cake, simply by running them on a local computer with a simple internet connection, applications using the *Atlas* toolkit will be accessible from the entire internet on laptops, smartphones, tablets…

## Content of the repository

The `atlastk` directory contains the *Perl* source code of the *Atlas* toolkit.

The `examples` directory contains some examples.

To run an example, launch, from within the `examples` directory, `perl -I../atlastk <Name>/main.pl`, where `<Name>` is the name of the example (`Blank`, `Chatroom`…).