---
title: "Практическое руководство. Фоновая загрузка файла | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
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
ms.assetid: 9b7bc5ae-051c-4904-9720-18f6667388bd
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Фоновая загрузка файла
Скачивание файла — это обычная задача, и было бы разумным запускать эту потенциально длительную операцию в отдельном потоке.  С помощью компонента <xref:System.ComponentModel.BackgroundWorker> и небольшого фрагмента кода эта задача легко решается.  
  
## Пример  
 В примере кода ниже демонстрируется использование компонента <xref:System.ComponentModel.BackgroundWorker> для загрузки XML\-файла с URL\-адреса.  Когда пользователь нажимает кнопку **Download** \(Скачать\), обработчик событий <xref:System.Windows.Forms.Control.Click> вызывает метод <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> компонента <xref:System.ComponentModel.BackgroundWorker> для запуска операции скачивания.  Кнопка отключается во время скачивания, а по его окончании снова становится активной.  В поле <xref:System.Windows.Forms.MessageBox> выводится содержимое файла.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#1)]  
  
 **Скачивание файла**  
  
 Файл скачивается в рабочем потоке компонента <xref:System.ComponentModel.BackgroundWorker>, который запускает обработчик событий <xref:System.ComponentModel.BackgroundWorker.DoWork>.  Этот поток запускается, когда код вызывает метод <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#3)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#3)]  
  
 **Ожидание завершения работы BackgroundWorker**  
  
 Обработчик событий `downloadButton_Click` демонстрирует ожидание завершения выполнения асинхронной задачи компонентом <xref:System.ComponentModel.BackgroundWorker>.  
  
 Если нужно, чтобы приложение лишь реагировало на события и не выполняло никакой работы в основном потоке в ожидании, пока не завершится выполнение фонового потока, просто завершите работу обработчика.  
  
 Если нужно продолжить выполнение работы в основном потоке, воспользуйтесь свойством <xref:System.ComponentModel.BackgroundWorker.IsBusy%2A>, чтобы определить, по\-прежнему ли выполняется поток <xref:System.ComponentModel.BackgroundWorker>.  В примере индикатор выполнения обновляется в процессе скачивания.  Для сохранения отклика пользовательского интерфейса обязательно вызовите метод <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#2)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#2)]  
  
 **Вывод результата**  
  
 Метод `backgroundWorker1_RunWorkerCompleted` обрабатывает событие <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> и вызывается по завершении фоновой операции.  Сначала этот метод проверяет свойство <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=fullName>.  Если свойство <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=fullName> имеет значение `null`, то метод выводит содержимое файла.  Затем он активирует кнопку скачивания, которая была отключена, когда началось скачивание, и сбрасывает индикатор выполнения.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#4)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#4)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System.Drawing, System.Windows.Forms и System.Xml.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Отказоустойчивость  
 Перед попыткой обращения к свойству <xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=fullName> или любому другому объекту, который может быть изменен обработчиком событий <xref:System.ComponentModel.BackgroundWorker.DoWork>, всегда проверяйте свойство <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=fullName> в обработчике событий <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
## См. также  
 <xref:System.ComponentModel.BackgroundWorker>   
 [Практическое руководство. Фоновое выполнение операции](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)