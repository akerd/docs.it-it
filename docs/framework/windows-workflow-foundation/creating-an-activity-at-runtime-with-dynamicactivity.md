---
title: "Creazione di un'attività in fase di esecuzione con DynamicActivity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d40fe3601cb8ad7c4f77cf50825da1deace5644e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a>Creazione di un'attività in fase di esecuzione con DynamicActivity
<xref:System.Activities.DynamicActivity> è una classe sealed concreta con costruttore pubblico. <xref:System.Activities.DynamicActivity> può essere usata per assemblare la funzionalità di attività in fase di esecuzione tramite un unico DOM di attività.  
  
## <a name="dynamicactivity-features"></a>Funzionalità DynamicActivity  
 La classe <xref:System.Activities.DynamicActivity> dispone dell'accesso alle proprietà, agli argomenti e alle variabili di esecuzione, ma non ai servizi in fase di esecuzione quali la pianificazione di attività figlio o il rilevamento.  
  
 Usando gli oggetti <xref:System.Activities.Argument> del flusso di lavoro è possibile impostare le proprietà di primo livello. Nel codice imperativo, questi argomenti vengono creati usando le proprietà CLR in un nuovo tipo. In XAML, vengono dichiarati usando i tag `x:Class` e `x:Member`.  
  
 Le attività costruite usando la classe <xref:System.Activities.DynamicActivity> si interfacciano con l'utilità di progettazione tramite l'oggetto <xref:System.ComponentModel.ICustomTypeDescriptor>. Le attività create nell'utilità di progettazione possono essere caricate usando il metodo <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> in modo dinamico, come dimostrato nella procedura riportata di seguito.  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a>Per creare un'attività in fase di esecuzione usando il codice imperativo  
  
1.  Aprire [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Selezionare **File**, **nuova**, **progetto**. Selezionare **Workflow 4.0** in **Visual c#** nel **tipi di progetto** window e selezionare il **v2010** nodo. Selezionare **applicazione Console flusso di lavoro sequenziale** nel **modelli** finestra. Assegnare il nome DynamicActivitySample al nuovo progetto.  
  
3.  Fare doppio clic su Workflow1 nel progetto HelloActivity e selezionare **eliminare**.  
  
4.  Aprire Program.cs. Aggiungere la seguente direttiva all'inizio del file.  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
5.  Sostituire il contenuto del metodo `Main` con il codice seguente che crea un'attività <xref:System.Activities.Statements.Sequence> che contiene una singola attività <xref:System.Activities.Statements.WriteLine> e la assegna alla proprietà <xref:System.Activities.DynamicActivity.Implementation%2A> di una nuova attività dinamica.  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =   
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =   
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6.  Eseguire l'applicazione. Una finestra della console con il testo "Hello World!" Consente di visualizzare.  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a>Per creare un'attività in fase di esecuzione usando il codice XAML  
  
1.  Aprire [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Selezionare **File**, **nuova**, **progetto**. Selezionare **Workflow 4.0** in **Visual c#** nel **tipi di progetto** window e selezionare il **v2010** nodo. Selezionare **applicazione Console flusso di lavoro** nel **modelli** finestra. Assegnare il nome DynamicActivitySample al nuovo progetto.  
  
3.  Aprire Workflow1.xaml nel progetto HelloActivity. Fare clic su di **argomenti** opzione nella parte inferiore della finestra di progettazione. Creare un nuovo argomento `In` denominato `TextToWrite` di tipo `String`.  
  
4.  Trascinare un **WriteLine** attività di **primitive** sezione della casella degli strumenti nell'area di progettazione. Assegnare il valore `TextToWrite` per il **testo** proprietà dell'attività.  
  
5.  Aprire Program.cs. Aggiungere la seguente direttiva all'inizio del file.  
  
    ```  
    using System.Activities.XamlIntegration;  
    ```  
  
6.  Sostituire il contenuto del metodo `Main` con il codice riportato di seguito.  
  
    ```  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7.  Eseguire l'applicazione. Una finestra della console con il testo "Hello World!" viene visualizzata.  
  
8.  Il file Workflow1 nel **Esplora** e selezionare **Visualizza codice**. Si noti che la classe di attività viene creata con `x:Class` e la proprietà viene creata con `x:Property`.  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di flussi di lavoro, attività ed espressioni tramite codice imperativo](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)  
 [DynamicActivityCreation](../../../docs/framework/windows-workflow-foundation/samples/dynamicactivity-creation.md)
