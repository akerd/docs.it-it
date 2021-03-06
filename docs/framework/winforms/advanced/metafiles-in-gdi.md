---
title: Metafile in GDI+
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b75ceb08df0454172a000d5d1ad15445f685ddf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="metafiles-in-gdi"></a>Metafile in GDI+
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]fornisce la <xref:System.Drawing.Imaging.Metafile> classe in modo che è possibile registrare e visualizzare metafile. Un metafile, denominato anche immagine vettore, è un'immagine che viene archiviata come una sequenza di comandi e le impostazioni di disegno. I comandi e le impostazioni di registrazione un <xref:System.Drawing.Imaging.Metafile> oggetto può essere archiviato in memoria o salvato in un file o flusso.  
  
## <a name="metafile-formats"></a>Formati Metafile  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]è possibile visualizzare metafile che sono stati archiviati nei formati seguenti:  
  
-   Metafile di Windows (WMF)  
  
-   Enhanced Metafile (EMF)  
  
-   EMF +  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]è possibile registrare metafile in formato EMF e EMF +, ma non nel formato WMF.  
  
 EMF + è un'estensione di EMF che consente [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record da archiviare. Esistono due varianti nel formato EMF +: EMF + solo ed EMF + Dual. Metafile EMF + solo contengono solo [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record. È possibile visualizzare tali metafile da [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ma non dal [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]. Metafile EMF + contengono [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record. Ogni [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record in un formato EMF + Dual metafile è associato a un'alternativa [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record. È possibile visualizzare tali metafile da [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] o [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 L'esempio seguente mostra un metafile precedentemente salvato come file. Metafile viene visualizzato con il relativo angolo superiore sinistro a (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Vedere anche  
 [Immagini, bitmap e metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
