# maude
* Introduction

  This repository contains Maude formalization for a submitted work ``DPL: A Language for GDPR Enforcement``. 


* Prerequisites

  To run and test the code, the rewriting tool [[http://maude.cs.illinois.edu/][Maude version 3.1]] is needed. It's
  downloadable free of charge from the University of Illinois. See the
  documentation there for installation instructions and further information.

* DPL's formalization in Maude

  DPL's data types are specified in the file datatypes.maude.
  DPL's operational semantics is specified in the file interpreter.maude.
  LTL formulas are specified in the file myModelCheck3.maude.
  Hygienic and non-hygienic programs are specified in the files hygienic.maude and non-hygienic.maude.

* Instructions

  Download Maude 3.1 and the files listed on /maude in the same directory.
  After installing Maude, to run the model checker and test the properties for our hygienic program, use the following commands in your terminal:
   1) sudo ./maude-Yices2.darwin64
   2) load datatypes.maude
   3) load interpreter.maude
   4) load hygienic.maude
   5) load model-checker.maude
   6) load myModelCheck3.maude
   7) red modelCheck(init, purposeLimitationconf(init, sensitive(str('mail),policy(2)), contract(str('MassMarketing),ob('MassMarketing0)))) .
   8) red modelCheck(init, storageLimitationconf(init, policy(2))) .
   9) the rest of properties are listed in Appendix B of the paper.

  To model check the properties in Appendix B, for the non-hygienic program, run the same commands listed previously, and in step 4, use `load non-hygienic.maude´    instead.
