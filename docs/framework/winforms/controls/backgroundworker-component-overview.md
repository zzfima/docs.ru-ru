---
title: "Общие сведения о компоненте BackgroundWorker | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BackgroundWorker"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "асинхронная модель"
  - "фоновые операции"
  - "фоновые задачи"
  - "BackgroundWorker - компонент"
  - "компоненты [Windows Forms], асинхронный"
  - "формы, фоновые операции"
  - "формы, многопоточность"
  - "работа с потоками [Windows Forms], фоновые операции"
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Общие сведения о компоненте BackgroundWorker
Выполнение многих часто выполняемых операций может занимать длительное время.  Например:  
  
-   Загрузка изображений  
  
-   Вызовы веб\-служб  
  
-   Скачивание и загрузка файлов \(в т. ч. через одноранговые приложения\)  
  
-   Сложные локальные вычисления  
  
-   Транзакции баз данных  
  
-   Обращение к локальному диску в случае низкой скорости по сравнению с доступом к памяти  
  
 Запуск таких операций может замедлить работу пользовательского интерфейса.  Если вы хотите получить отзывчивый пользовательский интерфейс, но столкнулись с длительными задержками в результате выполнения таких операций, удобным решением станет компонент <xref:System.ComponentModel.BackgroundWorker>.  
  
 Компонент <xref:System.ComponentModel.BackgroundWorker> позволяет выполнять длительные операции асинхронно \(в фоновом режиме\), т. е. в потоке, отличающемся от основного потока пользовательского интерфейса.  Для использование компонента <xref:System.ComponentModel.BackgroundWorker> необходимо только указать, какой рабочий метод обработки длительных операций будет выполняться в фоновом режиме, а затем вызвать метод <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.  Вызывающий поток продолжает работать нормально, в то время как рабочий метод работает асинхронно.  Когда метод закончит работу, компонент <xref:System.ComponentModel.BackgroundWorker> предупредит вызывающий поток событием <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>, которое может содержать результаты операции.  
  
 Компонент <xref:System.ComponentModel.BackgroundWorker> доступен на **Панели элементов**, вкладка **Компоненты**.  Чтобы добавить компонент <xref:System.ComponentModel.BackgroundWorker> в форму, перетащите компонент <xref:System.ComponentModel.BackgroundWorker> в соответствующую форму.  Он появится в области компонентов, а его свойства — в окне **Свойства**.  
  
 Для запуска асинхронной работы используйте метод <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.  <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> задействует опциональный параметр `object`, который может использоваться для передачи аргументов рабочему методу.  Класс <xref:System.ComponentModel.BackgroundWorker> показывает событие <xref:System.ComponentModel.BackgroundWorker.DoWork>, к которому обработчик событий <xref:System.ComponentModel.BackgroundWorker.DoWork> прикрепляет рабочий поток.  
  
 Обработчик событий <xref:System.ComponentModel.BackgroundWorker.DoWork> задействует параметр <xref:System.ComponentModel.DoWorkEventArgs> со свойством <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>.  Данное свойство получает параметр из <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> и может быть передано в рабочий метод, который будет вызываться в обработчике событий <xref:System.ComponentModel.BackgroundWorker.DoWork>.  В следующем примере показан способ назначения результата из рабочего метода, который называется `ComputeFibonacci`.  Он является частью большого примера, который можно найти по ссылке [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 Дополнительные сведения об использовании обработчиков событий см. в разделе [События](../../../../docs/standard/events/index.md).  
  
> [!CAUTION]
>  При использовании любой многопоточности существует потенциальная возможность возникновения серьезных ошибок.  Изучите раздел [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md), прежде чем применять какое\-либо решение с использованием многопоточности.  
  
 Дополнительные сведения об использовании класса <xref:System.ComponentModel.BackgroundWorker> см. в разделе [Практическое руководство. Фоновое выполнение операции](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
## См. также  
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/ru-ru/c731a50c-09c1-4468-9646-54c86b75d269)   
 [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)