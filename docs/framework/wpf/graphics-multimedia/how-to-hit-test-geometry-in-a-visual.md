---
title: 'Procedura: eseguire un hit test della geometria in un oggetto Visual'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ab125fe4031b5408eb202f21ce0fdf4314781f1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>Procedura: eseguire un hit test della geometria in un oggetto Visual
In questo esempio viene illustrato come eseguire un hit test su un oggetto visivo è costituito da uno o più <xref:System.Windows.Media.Geometry> oggetti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come recuperare il <xref:System.Windows.Media.DrawingGroup> da un oggetto visivo che utilizza il <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> metodo. Viene quindi eseguito un hit test sul contenuto di cui viene eseguito rendering di ogni tipo di disegno <xref:System.Windows.Media.DrawingGroup> per determinare la geometria raggiunta.  
  
> [!NOTE]
>  Nella maggior parte dei casi, si utilizzerebbe il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo per determinare se un punto interseca un contenuto di cui viene eseguito il rendering di un oggetto visivo.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 Il <xref:System.Windows.Media.Geometry.FillContains%2A> è un metodo di overload che consentono di eseguire l'hit test utilizzando un oggetto specificato <xref:System.Windows.Point> o <xref:System.Windows.Media.Geometry>. Se viene tracciata una geometria, il tratto può estendersi oltre i limiti del riempimento. In questo caso, si consiglia di chiamare <xref:System.Windows.Media.Geometry.StrokeContains%2A> oltre a <xref:System.Windows.Media.Geometry.FillContains%2A>.  
  
 È anche possibile fornire un <xref:System.Windows.Media.ToleranceType> utilizzato ai fini della conversione di Bézier.  
  
> [!NOTE]
>  Questo esempio non prende in considerazione eventuali trasformazioni o ritagli applicabili alla geometria. L'esempio, inoltre, non funziona con un controllo con stili, poiché a esso non saranno direttamente associati disegni.  
  
## <a name="see-also"></a>Vedere anche  
 [Hit testing a livello visivo](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [Eseguire un hit test utilizzando la geometria come parametro](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-geometry-as-a-parameter.md)
