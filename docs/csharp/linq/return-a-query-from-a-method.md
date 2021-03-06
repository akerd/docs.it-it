---
title: Ottenere una query da un metodo
description: Come ottenere una query.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: c1b69e3f5f0cd2c50ae80d2454e6b7f13dc30344
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a>Procedura: ottenere una query da un metodo (Guida per programmatori C#)
In questo esempio viene illustrato come ottenere una query da un metodo come valore restituito e come parametro `out`.  
  
 Gli oggetti di query sono componibili, vale a dire che è possibile ottenere una query da un metodo. Gli oggetti che rappresentano le query non memorizzano la raccolta risultante, ma piuttosto i passaggi da eseguire per ottenere i risultati quando necessario. Il vantaggio di ottenere oggetti query dai metodi è che gli oggetti possono essere ulteriormente composti o modificati. Di conseguenza, qualsiasi valore restituito o parametro `out` di un metodo che restituisce una query deve contenere anche quel tipo. Se un metodo materializza una query in un oggetto <xref:System.Collections.Generic.List%601> concreto o un tipo <xref:System.Array>, si ritiene che restituisca i risultati della query anziché la query stessa. Una variabile di query che viene restituita da un metodo può ancora essere composta o modificata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente il primo metodo restituisce una query come valore restituito e il secondo metodo restituisce una query come parametro `out`. Notare che in entrambi i casi è una query che viene restituita, non i risultati della query.  
  
 [!code-csharp[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a>Vedere anche  
 [Espressioni di query LINQ](index.md)
