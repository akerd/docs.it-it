---
title: 'Procedura: Creare un evento indirizzato personalizzato'
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
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e901242b265e0012f9ad65d9eaab89b1b63b40ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-routed-event"></a>Procedura: Creare un evento indirizzato personalizzato
Per l'evento personalizzato supportare il routing degli eventi, è necessario registrare un <xref:System.Windows.RoutedEvent> utilizzando il <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> metodo. Questo esempio illustra le nozioni di base per la creazione di un evento indirizzato personalizzato.  
  
## <a name="example"></a>Esempio  
 Come illustrato nell'esempio seguente, innanzitutto si registra un <xref:System.Windows.RoutedEvent> utilizzando il <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> metodo. Per convenzione, il <xref:System.Windows.RoutedEvent> nome del campo statico deve terminare con il suffisso ***evento***. In questo esempio, il nome dell'evento è `Tap` e la strategia di routing dell'evento è <xref:System.Windows.RoutingStrategy.Bubble>. Dopo la chiamata di registrazione, è possibile fornire funzioni di accesso di aggiunta e rimozione dell'evento [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] per l'evento.  
  
 Si noti che anche se l'evento viene generato tramite il metodo virtuale `OnTap` in questo particolare esempio, la modalità di generazione dell'evento o la relativa risposta alle modifiche varierà in base alle esigenze.  
  
 Si noti inoltre che in questo esempio viene implementata un'intera sottoclasse di <xref:System.Windows.Controls.Button>; tale sottoclasse è compilata come un assembly separato e quindi creare un'istanza come classe personalizzata in un apposito [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pagina. Ciò dimostra che i controlli sottoclassati possono essere inseriti in alberi composti da altri controlli e che, in una situazione del genere, gli eventi personalizzati in questi controlli dispongono delle stesse funzionalità di routing di qualsiasi elemento [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nativo.  
  
 [!code-csharp[RoutedEventCustom#CustomClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 Gli eventi di tunneling vengono creati lo stesso modo, ma con <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> impostato su <xref:System.Windows.RoutingStrategy.Tunnel> nella chiamata di registrazione. Per convenzione, gli eventi di tunneling in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono denominati con il prefisso "Preview".  
  
 Per un esempio di funzionamento degli eventi di bubbling, vedere [Gestire un evento indirizzato](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Cenni preliminari sull'input](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Cenni preliminari sulla modifica di controlli](../../../../docs/framework/wpf/controls/control-authoring-overview.md)
