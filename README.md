# *Perl* version of the *Atlas* toolkit

[![Run on Repl.it](https://repl.it/badge/github/epeios-q37/atlas-perl)](https://q37.info/s/h3h34zgq)  
[![Version 0.12](https://img.shields.io/static/v1.svg?&color=90b4ed&label=Version&message=0.12&style=for-the-badge)](http://github.com/epeios-q37/atlas-perl/)
[![Stars](https://img.shields.io/github/stars/epeios-q37/atlas-perl.svg?style=for-the-badge)](https://github.com/epeios-q37/atlas-perl/stargazers)
[![Forks](https://img.shields.io/github/forks/epeios-q37/atlas-perl.svg?style=for-the-badge)](https://github.com/epeios-q37/atlas-perl/network/members)
[![license: MIT](https://img.shields.io/github/license/epeios-q37/atlas-perl?color=yellow&style=for-the-badge)](https://github.com/epeios-q37/atlas-perl/blob/master/LICENSE)
[![Documentation](https://img.shields.io/static/v1?label=documentation&message=atlastk.org&color=ff69b4&style=for-the-badge)](https://atlastk.org)



> The [*Atlas* toolkit](https://atlastk.org) is available for:
> 
> | Language | *GitHub* repository| Online démonstrations | Stars 
> |-|-|-|-|
> | [*Java*](https://q37.info/s/qtnkp9w4) |<https://github.com/epeios-q37/atlas-java> | <https://q37.info/s/3vwk3h3n> | [![Stars](https://img.shields.io/github/stars/epeios-q37/atlas-java.svg?style=social)](https://github.com/epeios-q37/atlas-java/stargazers) |
> | [*Node.js*](https://q37.info/s/3d7hr733) | <https://github.com/epeios-q37/atlas-node> | <https://q37.info/s/st7gccd4> | [![Stars](https://img.shields.io/github/stars/epeios-q37/atlas-node.svg?style=social)](https://github.com/epeios-q37/atlas-node/stargazers) |
> | [*Perl*](https://q37.info/s/4nvmwjgg) |<https://github.com/epeios-q37/atlas-perl> | <https://q37.info/s/h3h34zgq> | [![Stars](https://img.shields.io/github/stars/epeios-q37/atlas-perl.svg?style=social)](https://github.com/epeios-q37/atlas-perl/stargazers) |
> | [*Python*](https://q37.info/s/pd7j9k4r) | <https://github.com/epeios-q37/atlas-python> | <https://q37.info/s/vwpsw73v> | [![Stars](https://img.shields.io/github/stars/epeios-q37/atlas-python.svg?style=social)](https://github.com/epeios-q37/atlas-python/stargazers) |
> | [*Ruby*](https://q37.info/s/gkfj3zpz) | <https://github.com/epeios-q37/atlas-ruby> | <https://q37.info/s/9thdtmjg> | [![Stars](https://img.shields.io/github/stars/epeios-q37/atlas-ruby.svg?style=social)](https://github.com/epeios-q37/atlas-ruby/stargazers) |

---

***Note for Repl.it users (online demonstrations)***: **after having launched a demonstration, you may have to click the refresh button (red arrow on picture below) top left in the frame containing the QR code to display it for the other demonstrations.**

[![The refresh button](https://q37.info/s/vsc3c7gc.png "The button to click to display the QR code")](http://q37.info/s/zbgfjtp9)

---



---

## Straight to the point: the [*Hello, World!*](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program) program

### Source code

```perl
use Atlas;

my $body = '
<div style="display: table; margin: 50px auto auto auto;">
 <fieldset>
  <input id="input" maxlength="20" placeholder="Enter a name here" type="text"
         data-xdh-onevent="Submit" value="World"/>
  <div style="display: flex; justify-content: space-around; margin: 5px auto auto auto;">
   <button data-xdh-onevent="Submit">Submit</button>
   <button data-xdh-onevent="Clear">Clear</button>
  </div>
 </fieldset>
</div>';

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

### Too good to be true? Try it now - it's quick and easy!

#### Online, with nothing to install

Thanks to [Replit](https://q37.info/s/mxmgq3qm), an [online IDE](https://q37.info/s/zzkzbdw7), you can write and run programs using the *Atlas* toolkit directly in your web browser, without having to install *Perl* on your computer.

To see some examples, like the following [*TodoMVC*](http://todomvc.com/) application or the above [*Hello, World!*](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program) program, simply:
- go [here](https://q37.info/s/h3h34zgq) (also accessible with the [![Run on Repl.it](https://repl.it/badge/github/epeios-q37/atlas-perl)](https://q37.info/s/h3h34zgq) badge on the top of this page),
-  click on the green `run` button,
-  select the demonstration you want to see,
-  click (or scan with your smartphone) the then displayed [QR code](https://q37.info/s/3pktvrj7),
- … and, as you wish, run your own tests directly in your web browser, by modifying the code of the examples or by writing your own code.

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

And, icing on the cake, simply by running them on a local computer with a simple internet connexion, applications using the *Atlas* toolkit will be accessible from the entire internet on laptops, smartphones, tablets…

## Content of the repository

The `atlastk` directory contains the *Perl* source code of the *Atlas* toolkit.

The `examples` directory contains some examples.

To run an example, launch, from within the `examples` directory, `perl -I../atlastk <Name>/main.pl`, where `<Name>` is the name of the example (`Blank`, `Chatroom`…).