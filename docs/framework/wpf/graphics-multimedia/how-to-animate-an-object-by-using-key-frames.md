---
title: 'Procedura: animare un oggetto utilizzando fotogrammi chiave'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71feb0ecef7a6356c95b843fbc2657ad2e4a7996
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>Procedura: animare un oggetto utilizzando fotogrammi chiave
In questo esempio viene illustrato come aggiungere un'animazione a un oggetto, ovvero in questo esempio il <xref:System.Windows.Controls.Page.Background%2A> proprietà di un <xref:System.Windows.Controls.Page> controllo, usando i fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> modifiche di classe per l'animazione di colore per il <xref:System.Windows.Controls.Page.Background%2A> proprietà di un <xref:System.Windows.Controls.Page> controllo. L'animazione di esempio modifica di un pennello di sfondo diversi a intervalli regolari. Viene utilizzata la <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> classe da creare tre fotogrammi chiave diversi. I fotogrammi chiave vengono utilizzati nel modo seguente:  
  
1.  Alla fine del primo secondo, aggiunge un'animazione a un'istanza di <xref:System.Windows.Media.LinearGradientBrush> classe. Questa sezione dell'esempio si applica una sfumatura lineare per il colore di sfondo in modo che il colore passa dal giallo arancione in rosso.  
  
2.  Alla fine del secondo successivo, aggiunge un'animazione a un'istanza di <xref:System.Windows.Media.RadialGradientBrush> classe. Questa sezione dell'esempio si applica una sfumatura radiale per il colore di sfondo in modo che il colore passa da bianco in blu in nero.  
  
3.  Al termine del terzo secondo animata un'istanza di <xref:System.Windows.Media.DrawingBrush> classe. Questa sezione dell'esempio si applica un motivo a scacchi allo sfondo.  
  
4.  L'animazione inizia nuovamente e viene ripetuta all'infinito.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>è l'unico tipo di un fotogramma chiave che è possibile utilizzare con la <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> classe. Fotogrammi chiave come <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> creano modifiche improvvise nei valori, vale a dire, le modifiche di colore in questo esempio si verificano improvvisamente.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.Page.Background%2A>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>  
 <xref:System.Windows.Media.LinearGradientBrush>  
 <xref:System.Windows.Media.RadialGradientBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Procedure relative ai fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
