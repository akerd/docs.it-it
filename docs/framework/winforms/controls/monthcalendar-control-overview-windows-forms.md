---
title: Cenni preliminari sul controllo MonthCalendar (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dba245df31ad14150e57188c95ab3a980ae8d3db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="monthcalendar-control-overview-windows-forms"></a>Cenni preliminari sul controllo MonthCalendar (Windows Form)
Windows Form <xref:System.Windows.Forms.MonthCalendar> controllo fornisce un'interfaccia grafica intuitiva per gli utenti di visualizzare e impostare le informazioni sulla data. Il controllo Visualizza un calendario: una griglia contenente i giorni del mese, distribuiti in colonne sotto i giorni della settimana, con l'intervallo di date evidenziato selezionato numerati. È possibile selezionare un altro mese facendo clic sui pulsanti freccia su entrambi i lati della didascalia del mese. A differenza dell'analoga <xref:System.Windows.Forms.DateTimePicker> controllo, è possibile selezionare più di una data con questo controllo. Per ulteriori informazioni sul <xref:System.Windows.Forms.DateTimePicker> di controllo, vedere [controllo DateTimePicker](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md).  
  
## <a name="configuring-the-monthcalendar-control"></a>Configurazione del controllo MonthCalendar  
 Il <xref:System.Windows.Forms.MonthCalendar> aspetto del controllo è configurabile. Per impostazione predefinita, la data odierna viene visualizzata un cerchio e viene anche indicata nella parte inferiore della griglia. È possibile modificare questa funzionalità impostando la <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> e <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> proprietà `false`. Inoltre, è possibile aggiungere numeri di settimana di calendario impostando il <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> proprietà `true`. Impostando il <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> proprietà, è possibile avere più mesi visualizzate orizzontalmente e verticalmente. Per impostazione predefinita, viene visualizzata domenica come primo giorno della settimana, ma è possibile designare qualsiasi giorno con il <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> proprietà.  
  
 È inoltre possibile impostare alcune date da visualizzare grassetto con cadenza occasionale, annuale o mensile, aggiungendo <xref:System.DateTime> oggetti per il <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>, e <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> proprietà. Per ulteriori informazioni, vedere [procedura: visualizzare giorni specifici in grassetto con il controllo MonthCalendar Windows Form](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md).  
  
 La proprietà chiave della <xref:System.Windows.Forms.MonthCalendar> controllo <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, l'intervallo di date selezionato nel controllo. Il <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> valore non può superare il numero massimo di giorni per cui può essere selezionato, impostare nel <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A> proprietà. Le date più recenti e meno recenti, l'utente può selezionare sono determinate dalle <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> e <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MonthCalendar>  
 [Controllo MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
