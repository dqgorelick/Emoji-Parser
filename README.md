##DESCRIPTION:

Currently there is no standardized way of interpretting emojis. Emojis are frequently used in text messages to represent a sentiment, but that exact sentiment can sometimes be ambiguous. We plan on making our own language to explore the application of emojis in natural language.

##SYNTAX DEFINITION

    programs    ::= Translate term
                | Sentence NounPhrase VerbPhrase
                | emojize term
                | analyze term
    Sentence    ::= NounPhrase VerbPhrase

    NounPhrase  ::= Adjective NounPhrase
                | Noun

    VerbPhrase  ::= Adverb VerbPhrase
                | Verb
    Adjective   ::= Term

    Verb        ::= Term

    Adverb      ::= Term

    Noun        ::= Term

    Term        ::= emoji
                | word

##OPERATIONAL SEMANTICS:

PARSER COMMANDS:

    text number: +14016486712
    [program-mode][terms]
    Program modes:
    --Analyze: takes emojis and performs sentiment analysis
    emojis -> sentiment

    --Emojize: takes sentence and translates into emojis
    sentence -> emojis

    --Translate: takes one emoji and translates into word
    emoji -> word

    --Sentence: takes emojis and translates into sentence
    emojis -> sentence

    Sentence :
    N(_,_)V(_,_) -> Adj,Noun Verb,Adv
    N(_)V(_,_)   -> Noun Verb,Adv
    N(_,_)V(_)   -> Adj,Noun Verb
    N(_)V(_)     -> Noun Verb

##STATIC ANALYSIS:

Type checking/Error message (Incorrect Syntax Error)
Still working this out, if you have any ideas?

##OTHER COMPONENTS:

We are creating an interpreter but are not sure how to integreate the compiler/optimization part of the project

##BACKEND TECHNOLOGIES:

    -Twilio API endpoint
    -Node.js server
    -hosting HTML site (maybe)
    -serverside services
    -HP – Haven on Demand or Semantria API