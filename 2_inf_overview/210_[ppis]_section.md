<!--- @file
  2.10 [Ppis] Section

  Copyright (c) 2007-2019, Intel Corporation. All rights reserved.<BR>

  Redistribution and use in source (original document form) and 'compiled'
  forms (converted to PDF, epub, HTML and other formats) with or without
  modification, are permitted provided that the following conditions are met:

  1) Redistributions of source code (original document form) must retain the
     above copyright notice, this list of conditions and the following
     disclaimer as the first lines of this file unmodified.

  2) Redistributions in compiled form (transformed to other DTDs, converted to
     PDF, epub, HTML and other formats) must reproduce the above copyright
     notice, this list of conditions and the following disclaimer in the
     documentation and/or other materials provided with the distribution.

  THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR
  IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
  MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
  EVENT SHALL TIANOCORE PROJECT  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
  SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
  PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;
  OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
  WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR
  OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF
  ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

-->

## 2.10 [Ppis] Section

The `[Ppis]` section of the EDK II INF file is a list of the global PPI C Names
that are used by the module developer. These C names are used by the parsing
utility to lookup the actual GUID value of the PPI that is located in the EDK
II package DEC files, and then emit a data structure to the module's `AutoGen.c`
file.

PPIs listed in architectural sections must not be listed in common `[Ppis]`
sections. The architectural section modifier is used as a restriction to mask
items from architectures that are not applicable.

This section uses one of the following section definitions:

```ini
[Ppis]
[Ppis.common]
[Ppis.IA32]
[Ppis.X64]
[Ppis.EBC]
```

The formats for entries in this section is:

`gEfiPpiCName [ | FeatureFlagExpression ] ## Usage comment`

When a `FeatureFlagExpression` is present, if the expression evaluates to
`TRUE`, then the PPI entry is valid. If the expression evaluates to `FALSE`,
then the EDK II build tools must ignore the entry.

The following is an example of the `[Ppis]` section.

```ini
[Ppis]
  gEfiPeiMemoryDiscoveredPpiGuid
  gEfiFindFvPpiGuid
```
