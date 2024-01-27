<div align="center">

The *Atlas* toolkit is available for:

[![Java](https://s.q37.info/jrnv4mj4.svg)](https://github.com/epeios-q37/atlas-java) [![Node.js](https://s.q37.info/fh7v7kn9.svg)](https://github.com/epeios-q37/atlas-node) [![Perl](https://s.q37.info/hgnwnnn3.svg)](https://github.com/epeios-q37/atlas-perl) [![Python](https://s.q37.info/94937nbb.svg)](https://github.com/epeios-q37/atlas-python) [![Ruby](https://s.q37.info/zn4qrx9j.svg)](https://github.com/epeios-q37/atlas-ruby)

To see the *Atlas* toolkit in action:

[![Version 0.13](https://img.shields.io/static/v1.svg?&color=blue&labelColor=red&label=online&message=demonstrations&style=for-the-badge)](https://s.q37.info/sssznrb4)

</div>



# *Perl* version of the *Atlas* toolkit

<div align="center">

[![Version 0.13](https://img.shields.io/static/v1.svg?&color=90b4ed&label=Version&message=0.13&style=for-the-badge)](http://github.com/epeios-q37/atlas-perl/) [![license: MIT](https://img.shields.io/github/license/epeios-q37/atlas-perl?color=yellow&style=for-the-badge)](https://github.com/epeios-q37/atlas-perl/blob/master/LICENSE) [![Documentation](https://img.shields.io/static/v1?label=documentation&message=atlastk.org&color=ff69b4&style=for-the-badge)](https://atlastk.org) 

</div>



## A GUI with *Perl* in a couple of minutes

Click the animation to see a screencast of programming this ["Hello, World!" program](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program) with *Perl* in a matter of minutes:

<div align="center">

[![Building a GUI in with *Perl* in less then 10 minutes](https://s.q37.info/qp4z37pg.gif)](https://s.q37.info/3g7zdnp7)

</div>

Same video on [*Peertube*](https://en.wikipedia.org/wiki/PeerTube): <https://s.q37.info/bvvjj7gk>.

<details>
<summary>Click to see the corresponding source code</summary>

```perl
use Atlas;
 
my $BODY = '
<fieldset>
 <input id="Input" xdh:onevent="Submit" value="World"/>
 <button xdh:onevent="Submit">Hello</button>
 <hr/>
 <fieldset>
  <output id="Output">Greetings displayed here!</output>
 </fieldset>
</fieldset>
';
 
sub acConnect {
 my ($hello, $dom) = @_;
 
 $dom->inner("", $BODY);
 $dom->focus("Input");
}
 
sub acSubmit {
 my ($hello, $dom) = @_;
 my $name = $dom->getValue("Input");
 
 $dom->begin("Output", "<div>Hello, $name!</div>");
 $dom->setValue("Input", "");
 $dom->focus("Input");
}
 
my %CALLBACKS = (
 "" => \&acConnect,
 "Submit" => \&acSubmit
);
 
Atlas::launch(\%CALLBACKS);
```

</details>

### See for yourself right now - it's quick and easy!

```shell
# You can replace 'github.com' with 'framagit.org'.
# DON'T copy/paste this and above line!
git clone https://github.com/epeios-q37/atlas-perl
cd atlas-perl/examples
perl -I ../atlastk Hello/Hello.pl
```



## Your turn

If you want to take your code to the next level, from [CLI](https://s.q37.info/cnh9nrw9) to [GUI](https://s.q37.info/hw9n3pjs), then you found the right toolkit.

With the [*Atlas* toolkit](http://atlastk.org/), you transform your programs in modern web applications ([*SPA*](https://s.q37.info/7sbmxd3j)) without the usual hassles:
- no *JavaScript* to write; only *HTML*(/*CSS*) and *Perl*,
- no [front and back end architecture](https://s.q37.info/px7hhztd) to bother with,
- no [web server](https://s.q37.info/n3hpwsht) (*Apache*, *Nginx*…) to install,
- no need to deploy your application on a remote server,
- no incoming port to open on your internet box or routeur.

The *Atlas* toolkit is written in pure *Perl*, with no native code and no dependencies, allowing the *Atlas* toolkit to be used on all environments where *Perl* is available. 

And simply by running them on a local computer connected to internet, applications using the *Atlas* toolkit will be accessible from the entire internet on laptops, smartphones, tablets…

## Content of the repository

The `atlastk` directory contains the *Perl* source code of the *Atlas* toolkit.

The `examples` directory contains some examples.

To run an example, launch, from within the `examples` directory, `perl -I../atlastk <Name>/main.pl`, where `<Name>` is the name of the example (`Blank`, `Chatroom`…).
