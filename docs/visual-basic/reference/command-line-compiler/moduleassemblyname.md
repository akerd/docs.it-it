---
title: /moduleassemblyname
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d9a5307970ac745b4f102d0008e64b985c00e52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="moduleassemblyname"></a>/moduleassemblyname
Specifica il nome dell'assembly di cui fa parte il modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`assembly_name`|Il nome dell'assembly che farà parte questo modulo.|  
  
## <a name="remarks"></a>Note  
 Il compilatore elabora il `/moduleassemblyname` solo se opzione il `/target:module` è stata specificata l'opzione. In questo modo il compilatore di creare un modulo. Il modulo creato dal compilatore è valido solo per l'assembly specificato con il `/moduleassemblyname` opzione. Se si inserisce il modulo in un assembly diverso, si verificheranno errori di runtime.  
  
 Il `/moduleassemblyname` opzione è necessaria solo quando vengono soddisfatte le seguenti:  
  
-   Un tipo di dati del modulo deve accedere a un `Friend` tipo in un assembly di riferimento.  
  
-   L'assembly di riferimento ha concesso l'accesso all'assembly friend all'assembly in cui il modulo verrà compilato.  
  
 Per ulteriori informazioni sulla creazione di un modulo, vedere [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Per ulteriori informazioni sugli assembly friend, vedere [assembly Friend](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).  
  
> [!NOTE]
>  Il `/moduleassemblyname` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo quando esegue la compilazione da un prompt dei comandi.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Compilare un assembly su più file](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [/main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [Assembly e Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Assembly Friend](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)
