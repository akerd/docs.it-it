---
title: 'Procedura: partizionare lo spazio utilizzando l''elemento DockPanel'
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
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 056aeaf1dfb7db420ce5359849a9a409dcd3fe13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a>Procedura: partizionare lo spazio utilizzando l'elemento DockPanel
Nell'esempio seguente viene creato un semplice [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework utilizzando un <xref:System.Windows.Controls.DockPanel> elemento. Il <xref:System.Windows.Controls.DockPanel> partiziona lo spazio disponibile per i relativi elementi figlio.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il <xref:System.Windows.Controls.DockPanel.Dock%2A> proprietà, che è una proprietà associata, per ancorare due identici <xref:System.Windows.Controls.Border> gli elementi in corrispondenza di <xref:System.Windows.Controls.Dock.Top> dello spazio partizionato. Una terza <xref:System.Windows.Controls.Border> per l'elemento è ancorato il <xref:System.Windows.Controls.Dock.Left>, con larghezza impostata su 200 pixel. Un quarto <xref:System.Windows.Controls.Border> è ancorato il <xref:System.Windows.Controls.Dock.Bottom> dello schermo. L'ultimo <xref:System.Windows.Controls.Border> elemento riempie automaticamente lo spazio rimanente.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  Per impostazione predefinita, l'ultimo elemento figlio di un <xref:System.Windows.Controls.DockPanel> elemento riempie il rimanente spazio non allocato. Se non si desidera questo comportamento, impostare `LastChildFill="False"`.  
  
 L'applicazione compilata crea una nuova interfaccia utente analoga alla seguente.  
  
 ![Scenario DockPanel tipico.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.DockPanel>  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
