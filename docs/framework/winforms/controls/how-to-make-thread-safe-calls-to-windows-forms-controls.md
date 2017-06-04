---
title: "Практическое руководство. Осуществление потокобезопасных вызовов элементов управления Windows Forms. | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EHInvalidOperation.WinForms.IllegalCrossThreadCall"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "потокобезопасность, вызов элементов управления [Windows Forms]"
  - "вызов элементов управления, потокобезопасность [Windows Forms]"
  - "CheckForIllegalCrossThreadCalls - свойство [Windows Forms]"
  - "элементы управления Windows Forms, многопоточность"
  - "класс BackgroundWorker, примеры"
  - "работа с потоками [Windows Forms], межпоточные вызовы"
  - "элементы управления [Windows Forms], многопоточность"
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Осуществление потокобезопасных вызовов элементов управления Windows Forms.
При использовании многопоточности для улучшения производительности приложений Windows Forms во время вызова элементов управления необходимо соблюдать принципы безопасности потоков.  
  
 Доступ к элементам управления Windows Forms по сути не является потокобезопасным. При наличии двух или более потоков, контролирующих состояние элемента управления, этот элемент управления можно перевести в несогласованное состояние. Кроме того, могут возникнуть другие ошибки, связанные с потоками, включая состояния гонки и взаимоблокировки. Очень важно обеспечить потокобезопасный доступ к элементам управления.  
  
 Вызов элемента управления из каких\-либо других потоков, за исключением потока, в котором был создан элемент управления, без использования метода <xref:System.Windows.Forms.Control.Invoke%2A> является нарушением безопасности. Ниже приведен пример вызова, который не является потокобезопасным.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#6)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#6)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#6)]  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] помогает выявлять обращения к элементам управления, выполненные с нарушением безопасности потока. Если приложение выполняется в отладчике, а поток, отличный от создавшего элемент управления, пытается вызывать этот элемент управления, в отладчике создается исключение <xref:System.InvalidOperationException> с сообщением "Обращение к элементу управления *имя элемента управления* из потока, не являющегося создателем данного элемента управления".  
  
 Это исключение всегда возникает во время отладки, а в некоторых случаях во время выполнения. Исключение может появляться при отладке приложений, написанных с использованием версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], выпущенной ранее [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. Эту проблему настоятельно рекомендуется устранить при ее обнаружении, но предупреждение об ошибке можно отключить, задав свойству <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A> значение `false`. В результате элемент управления будет работать так же, как в Visual Studio .NET 2003 и [!INCLUDE[net_v11_short](../../../../includes/net-v11-short-md.md)].  
  
> [!NOTE]
>  При использовании элементов управления ActiveX в форме может может возникнуть несколько исключений <xref:System.InvalidOperationException> в разных потоках, если выполнение осуществляется в отладчике. В таких случаях элемент управления ActiveX не поддерживает многопоточность. Дополнительные сведения об использовании элементов управления ActiveX в Windows Forms см. в разделе [Windows Forms and Unmanaged Applications](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md). При использовании Visual Studio этого исключения можно избежать, отключив ведущий процесс Visual Studio. Сведения см. в разделе [Практическое руководство. Отключение главного процесса](../Topic/How%20to:%20Disable%20the%20Hosting%20Process.md).  
  
## Осуществление потокобезопасных вызовов элементов управления Windows Forms  
  
#### Осуществление потокобезопасного вызова элемента управления Windows Forms  
  
1.  Запросите свойство <xref:System.Windows.Forms.Control.InvokeRequired%2A> элемента управления.  
  
2.  Если <xref:System.Windows.Forms.Control.InvokeRequired%2A> возвращает `true`, вызовите <xref:System.Windows.Forms.Control.Invoke%2A> с делегатом, фактически вызывающим элемент управления.  
  
3.  Если <xref:System.Windows.Forms.Control.InvokeRequired%2A> возвращает `false`, вызовите элемент управления напрямую.  
  
 В следующем примере кода потокобезопасный вызов реализуется в методе `ThreadProcSafe`, который выполняется в фоновом потоке. Если свойство <xref:System.Windows.Forms.TextBox> элемента управления <xref:System.Windows.Forms.Control.InvokeRequired%2A> возвращает значение `true`, метод `ThreadProcSafe` создает экземпляр `SetTextCallback` и передает его в метод <xref:System.Windows.Forms.Control.Invoke%2A> формы. В результате метод `SetText` будет вызван в потоке, создавшем элемент управления <xref:System.Windows.Forms.TextBox>. В таком контексте свойство <xref:System.Windows.Forms.Control.Text%2A> задается напрямую.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#7)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#7)]  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#3)]  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#8](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#8)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#8)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#8)]  
  
## Осуществление потокобезопасных вызовов с помощью компонента BackgroundWorker  
 Наиболее предпочтительным способом реализации многопоточности в приложении является использование компонента <xref:System.ComponentModel.BackgroundWorker>. Для реализации многопоточности компонент <xref:System.ComponentModel.BackgroundWorker> использует модель на основе событий. Фоновый поток запускает обработчик событий <xref:System.ComponentModel.BackgroundWorker.DoWork>, а поток, создающий элементы управления, запускает обработчики событий <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> и <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>. Элементы управления можно вызывать из обработчиков событий <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> и <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
#### Осуществление потокобезопасных вызовов с помощью компонента BackgroundWorker  
  
1.  Создайте метод для выполнения действий, которые должны осуществляться в фоновом потоке. Элементы управления, созданные основным потоком в этот методе, вызывать не следует.  
  
2.  Создайте метод для сообщения о результатах работы фонового потока после его завершения. В этом методе можно вызывать элементы управления, созданные основным потоком.  
  
3.  Привяжите метод, созданный на шаге 1, к событию <xref:System.ComponentModel.BackgroundWorker.DoWork> экземпляра <xref:System.ComponentModel.BackgroundWorker>, и привяжите метод, созданный в шаге 2, к событию <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> того же экземпляра.  
  
4.  Чтобы запустить фоновый поток, вызовите метод <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> экземпляра <xref:System.ComponentModel.BackgroundWorker>.  
  
 В следующем примере кода обработчик событий <xref:System.ComponentModel.BackgroundWorker.DoWork> использует <xref:System.Threading.Thread.Sleep%2A> для моделирования заданий, на выполнение которых уходит определенное время. Он не вызывает элемент управления <xref:System.Windows.Forms.TextBox> формы. Свойство <xref:System.Windows.Forms.TextBox> элемента управления <xref:System.Windows.Forms.Control.Text%2A> задается непосредственно в обработчике событий <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#5)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#5)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#5)]  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#9)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#9)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#9)]  
  
 Составить отчет о ходе выполнения в фоновой задачи можно также с помощью события <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>. Пример, который содержит это событие, см. в разделе <xref:System.ComponentModel.BackgroundWorker>.  
  
## Пример  
 В следующем примере кода представлено полное приложение Windows Forms, состоящее из формы с тремя кнопками и одного текстового поля. Первая кнопка показывает доступ с нарушением принципов безопасности нескольких потоков, вторая кнопка показывает безопасный доступ с использованием <xref:System.Windows.Forms.Control.Invoke%2A>, а третья кнопка показывает безопасный доступ с использованием <xref:System.ComponentModel.BackgroundWorker>.  
  
> [!NOTE]
>  Инструкции по запуску этого примера см. в разделе [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/ru-ru/cc447f7e-4c3b-4397-9d05-aeba3ca49416). Для этого примера требуются ссылки на сборки System.Drawing и System.Windows.Forms.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#1)]  
  
 Если запустить приложение и нажать кнопку **Небезопасный вызов**, в текстовом поле немедленно появится текст "Создано основным потоком". Через две секунды, если предпринимается попытка осуществления небезопасного вызова, отладчик Visual Studio показывает, что создано исключение. Отладчик останавливается в строке фонового потока, которая пыталась создать запись непосредственно в текстовом поле. Необходимо перезапустить приложение, чтобы протестировать две другие кнопки. Если нажать кнопку **Безопасный вызов**, в текстовом поле появляется текст "Создано основным потоком". Через две секунды в текстовом поле появляется текст "Создано фоновым потоком \(Invoke\)", что означает, что был вызван метод <xref:System.Windows.Forms.Control.Invoke%2A>. Если нажать кнопку **Безопасный вызов BW**, в текстовом поле появляется текст "Создано основным потоком". Через две секунды в текстовом поле появляется текст "Создано основным потоком после завершения работы фонового потока", что означает, что был вызван обработчик события <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> объекта <xref:System.ComponentModel.BackgroundWorker>.  
  
## Отказоустойчивость  
  
> [!CAUTION]
>  При использовании многопоточности любого вида код может быть подвержен весьма серьезным и сложным ошибкам. Перед реализацией любого решения, использующего многопоточность, ознакомьтесь со сведениями в разделе [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md).  
  
## См. также  
 <xref:System.ComponentModel.BackgroundWorker>   
 [Практическое руководство. Фоновое выполнение операции](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [Разработка пользовательских элементов управления Windows Forms в .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Windows Forms and Unmanaged Applications](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)