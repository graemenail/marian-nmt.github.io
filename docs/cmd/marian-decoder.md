---
layout: docs
title: Command-line options for marian-decoder
permalink: /docs/cmd/marian-decoder
icon: fa-file-code-o
---


## General options
```
-c [ --config ] arg                     Configuration file
-w [ --workspace ] arg (=512)           Preallocate  arg  MB of work space
--log arg                               Log training process information to file given by  arg
--log-level arg (=info)                 Set verbosity level of logging (trace - debug - info - warn - err(or) - critical - off)
--quiet                                 Suppress all logging to stderr. Logging to files still works
--seed arg (=0)                         Seed for all random number generators. 0 means initialize randomly
--relative-paths                        All paths are relative to the config file location
--dump-config                           Dump current (modified) configuration to stdout and exit
--version                               Print version number and exit
-h [ --help ]                           Print this help message and exit
```

## Model options
```
-m [ --models ] arg                     Paths to model(s) to be loaded
--type arg (=amun)                      Model type (possible values: amun, nematus, s2s, multi-s2s, transformer)
--dim-vocabs arg (=0 0)                 Maximum items in vocabulary ordered by rank, 0 uses all items in the provided/created vocabulary file
--dim-emb arg (=512)                    Size of embedding vector
--dim-rnn arg (=1024)                   Size of rnn hidden state
--enc-type arg (=bidirectional)         Type of encoder RNN : bidirectional, bi-unidirectional, alternating (s2s)
--enc-cell arg (=gru)                   Type of RNN cell: gru, lstm, tanh (s2s)
--enc-cell-depth arg (=1)               Number of tansitional cells in encoder layers (s2s)
--enc-depth arg (=1)                    Number of encoder layers (s2s)
--dec-cell arg (=gru)                   Type of RNN cell: gru, lstm, tanh (s2s)
--dec-cell-base-depth arg (=2)          Number of tansitional cells in first decoder layer (s2s)
--dec-cell-high-depth arg (=1)          Number of tansitional cells in next decoder layers (s2s)
--dec-depth arg (=1)                    Number of decoder layers (s2s)
--skip                                  Use skip connections (s2s)
--layer-normalization                   Enable layer normalization
--best-deep                             Use Edinburgh deep RNN configuration (s2s)
--special-vocab arg                     Model-specific special vocabulary ids
--tied-embeddings                       Tie target embeddings and output embeddings in output layer
--tied-embeddings-src                   Tie source and target embeddings
--tied-embeddings-all                   Tie all embedding layers and output layer
--transformer-heads arg (=8)            Number of head in multi-head attention (transformer)
--transformer-dim-ffn arg (=2048)       Size of position-wise feed-forward network (transformer)
--transformer-preprocess arg            Operation before each transformer layer: d = dropout, a = add, n = normalize
--transformer-postprocess-emb arg (=d)  Operation after transformer embedding layer: d = dropout, a = add, n = normalize
--transformer-postprocess arg (=dan)    Operation after each transformer layer: d = dropout, a = add, n = normalize
```

## Translator options
```
-i [ --input ] arg (=stdin)             Paths to input file(s), stdin by default
-v [ --vocabs ] arg                     Paths to vocabulary files have to correspond to --input
-b [ --beam-size ] arg (=12)            Beam size used during search
-n [ --normalize ] [=arg(=1)] (=0)      Divide translation score by pow(translation length, arg) 
--allow-unk                             Allow unknown words to appear in output
--max-length arg (=1000)                Maximum length of a sentence in a training sentence pair
-d [ --devices ] arg (=0)               GPUs to use for translating
--mini-batch arg (=1)                   Size of mini-batch used during update
--maxi-batch arg (=1)                   Number of batches to preload for length-based sorting
--n-best                                Display n-best list
--weights arg                           Scorer weights
-p [ --port ] arg (=8080)               Port number for web socket server
```
Version: 
v1.0.0+83f3b35