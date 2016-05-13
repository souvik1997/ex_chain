# ExChain

Very simple Markov Chain written in Elixir. This is my toy-project, so I can learn Elixir.

If you have experience with Elixir and find improvements, please let me know, or simply write a comment in the appropiate line. All suggestions are more than welcome.

It's mostly based in the [Markov Models in Ruby](https://docs.omniref.com/github/omniref/hn_title_generator/0.1.0/symbols/HNTitleGenerator::MarkovModel#line=11) tutorial.

The Markov Model creates funny messages based on tweets downloaded from your Twitter Archive.

It generates messages [like this](https://twitter.com/eljojo/status/730268186369646592).

## How to run this?

The first thing you need is Elixir. If you have a Mac, you can install it using ``brew install elixir``.

This program needs your twitter archive, so go ahead and dowload it from your settings in twitter.com.

Download the repository with ``git clone git@github.com:eljojo/ex_chain.git``.
Extract your twitter archive, and put the contents of the ``data/js/tweets`` folder into ``ex_chain/data``.

```
$ cd ex_chain
$ mix deps.get # get the dependencies using mix, Elixir's rake. Analog to bundle install.
$ iex -S mix # analog to irb or rails console
```

Inside iex, you can generate new messages by typing:

```elixir
iex(1)> ExChain.create_filtered_sentence
{:ok, "I'm not a Food Social Network?", 0.4668037713169559, 4}
iex(2)> ExChain.create_filtered_sentence
{:ok, "I am in churros.", 0.30839889769910056, 2}
iex(3)> ExChain.create_filtered_sentence
{:ok, "I'm never sleeping again.", 0.3546596799639396, 14}
iex(4)> ExChain.create_sentence
{"future: scumbag apple: makes you release the happiness hormone.",
 0.8334241103848947}
iex(5)> ExChain.complete_sentence("i love")
{"i love the smell of shipping technical debt", 0.6685185185185185}
```

## Where's the code?

The meat and potatos are located in just three files:

| lib/ex_chain/datasource.ex   | This file parses the tweets located in the data folder.            |
|------------------------------|--------------------------------------------------------------------|
| lib/ex_chain/markov_model.ex | This file is in charge of holding the state of the "Markov Model". |
| lib/ex_chain.ex              | This file generates the sentences using the Markov Model.          |

As soon as I find more time, I'll document as much as I can.

Please send me all your suggestions to [@eljojo](https://twitter.com/eljojo) or directly to my email jojo at eljojo dot net.