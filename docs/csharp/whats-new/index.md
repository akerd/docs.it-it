---
title: "Novità di C# - Guida a C#"
description: Informazioni sull'evoluzione del linguaggio C#
keywords: "C#, funzionalità più recenti, novità, Roslyn"
author: BillWagner
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.translationtype: HT
ms.sourcegitcommit: df0438dd742db802bb0f935d840006236d5d9bf9
ms.openlocfilehash: 0a328f62a02aea223340fcc00e839e841041a7d6
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---

# <a name="whats-new-in-c"></a>Novità di C# #

Questa pagina offre un riepilogo delle nuove funzionalità in ogni versione principale del linguaggio C#. I collegamenti seguenti indirizzano a informazioni dettagliate sulle funzionalità principali aggiunte in ogni versione.

> [!IMPORTANT]
> Il linguaggio C# si basa sui tipi e metodi in una *libreria standard* per alcune delle funzionalità. Un esempio è l'elaborazione delle eccezioni. Ogni istruzione o espressione `throw` viene controllata per assicurarsi che l'oggetto generato derivi da @System.Exception. Analogamente, ogni istruzione `catch` viene controllata per verificare che il tipo intercettato derivi da @System.Exception. In ogni versione potrebbero essere aggiunti nuovi requisiti. Per usare le funzionalità del linguaggio più recenti in ambienti meno recenti, potrebbe essere necessario installare librerie specifiche. Questi requisiti sono documentati nella pagina per ogni versione specifica. Le informazioni sulle [relazioni tra linguaggio e libreria](relationships-between-language-and-library.md) possono essere utili per comprendere meglio questa dipendenza. 

* [C# 7.1](csharp-7-1.md):
    - Questa pagina descrive le funzionalità più recenti del linguaggio C#. La descrizione riguarda C# 7.1, attualmente disponibile in [Visual Studio 2017 versione 15.3](https://www.visualstudio.com/vs/whatsnew/) e in [.NET Core 2.0 SDK](../../core/whats-new/index.md).

* [C# 7](csharp-7.md):
    - Questa pagina descrive le funzionalità aggiunte in C# 7. Questi elementi sono stati aggiunti in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) e [.NET Core 1.0](../../core/whats-new/index.md) e versioni successive
     
* [C# 6](csharp-6.md):
    - Questa pagina descrive le funzionalità che sono state aggiunte in C# 6. Queste funzionalità sono disponibili in Visual Studio 2015 per gli sviluppatori Windows e in .NET Core 1.0 per gli sviluppatori che vogliono esplorare il linguaggio C# in macOS e Linux.

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* [Supporto per più piattaforme](../../core/index.md):
    - Grazie al supporto per .NET Core, è possibile eseguire C# su diverse piattaforme. Gli utenti interessati a provare C# in macOS o su una delle diverse distribuzioni Linux supportate possono leggere le informazioni relative a .NET Core.

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a>Versioni precedenti
Di seguito sono elencate le principali funzionalità introdotte in versioni precedenti del linguaggio C# e Visual Studio .NET.  
  
 * Visual Studio .NET 2013: 
     - Questa versione di Visual Studio include correzioni di bug, miglioramenti delle prestazioni e Technology Preview di .NET Compiler Platform ("Roslyn") che è diventato .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.

 * C# 5, Visual Studio .NET 2012: 
     - `Async` / `await` e attributi delle [informazioni sul chiamante](../programming-guide/concepts/caller-information.md).

 * C# 4, Visual Studio .NET 2010: 
     - `Dynamic`, [argomenti denominati](../programming-guide/classes-and-structs/named-and-optional-arguments.md), parametri facoltativi, [covarianza e controvarianza](../programming-guide/concepts/covariance-contravariance/index.md) generiche.

 * C# 3, Visual Studio .NET 2008: 
     - Inizializzatori di oggetto e di raccolta, espressioni lambda, metodi di estensione, tipi anonimi, proprietà automatiche, inferenza del tipo `var` locale e [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).

 * C# 2, Visual Studio .NET 2005: 
     - Metodi anonimi, generics, tipi nullable, iteratori/yield, classi `static`, covarianza e controvarianza per i delegati.

 * C# 1.1, Visual Studio .NET 2003: 
     - Pragma `#line` e commenti documento xml.

 * C# 1, Visual Studio .NET 2002: 
     - La prima versione di [C#](../csharp.md).   

