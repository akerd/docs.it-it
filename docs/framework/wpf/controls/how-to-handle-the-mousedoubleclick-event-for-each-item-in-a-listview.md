---
title: 'Procedura: gestire l''evento MouseDoubleClick per ciascun elemento di ListView'
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
helpviewer_keywords: ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53c40e9e3b02bdf33a073a93d28b619e399e375f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Procedura: gestire l'evento MouseDoubleClick per ciascun elemento di ListView
Per gestire un evento per un elemento in un <xref:System.Windows.Controls.ListView>, è necessario aggiungere un gestore eventi a ogni <xref:System.Windows.Controls.ListViewItem>. Quando un <xref:System.Windows.Controls.ListView> è associato a un'origine dati, è necessario creare in modo esplicito un <xref:System.Windows.Controls.ListViewItem>, ma è possibile gestire l'evento per ogni elemento aggiungendo un <xref:System.Windows.EventSetter> a uno stile di un <xref:System.Windows.Controls.ListViewItem>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un'associazione a dati <xref:System.Windows.Controls.ListView> e crea un <xref:System.Windows.Style> per aggiungere un gestore eventi a ogni <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 L'esempio seguente viene gestito il <xref:System.Windows.Controls.Control.MouseDoubleClick> evento.  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  Sebbene sia più comune per associare un <xref:System.Windows.Controls.ListView> a un'origine dati, è possibile utilizzare uno stile per aggiungere un gestore eventi a ogni <xref:System.Windows.Controls.ListViewItem> in un'associazione di dati non <xref:System.Windows.Controls.ListView> indipendentemente dal fatto se si crea in modo esplicito un <xref:System.Windows.Controls.ListViewItem>.  Per ulteriori informazioni su creati in modo esplicito e in modo implicito <xref:System.Windows.Controls.ListViewItem> controlli, vedere <xref:System.Windows.Controls.ItemsControl>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.XmlElement>  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [Panoramica sul controllo ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
