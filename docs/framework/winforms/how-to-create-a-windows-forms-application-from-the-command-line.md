---
title: "How to: Create a Windows Forms Application from the Command Line | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, application development from command line"
  - "Windows Forms, getting started"
  - "Windows Forms, creating basic form"
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Create a Windows Forms Application from the Command Line
В процедурах ниже описаны основные шаги, которые необходимо выполнить для создания и запуска приложения Windows Forms из командной строки.  Visual Studio предлагает расширенную поддержку этих процедур.  См. также [Пошаговое руководство. Создание простой формы в Windows Forms](http://msdn.microsoft.com/library/z9w2f38k\(v=vs.110\)).  
  
## Процедура  
  
#### Создание формы  
  
1.  В пустом файле кода введите следующие операторы import или using:  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2.  Объявите класс с именем `Form1`, наследуемый от класса Form.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3.  Создайте конструктор по умолчанию для класса `Form1`.  
  
     В следующий процедуре будет добавлен дополнительный код конструктора.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4.  Добавьте в класс метод `Main`.  
  
    1.  Примените <xref:System.STAThreadAttribute> к методу `Main`, чтобы указать, что приложение Windows Forms использует однопотоковое подразделение.  
  
    2.  Вызовите <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> для придания приложению внешнего вида в стиле Windows XP.  
  
    3.  Создайте экземпляр формы и запустите его.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### Компиляция и запуск приложения  
  
1.  В командной строке .NET Framework перейдите к папке, в которой содержится класс `Form1`.  
  
2.  Скомпилируйте форму.  
  
    -   При использования языка C\# введите `csc form1.cs`  
  
         `-или-`  
  
    -   Если используется Visual Basic, введите `vbc form1.vb /r:system.dll,system.drawing.dll,system.windows.forms.dll`  
  
3.  В командной строке введите `Form1.exe`  
  
## Добавление элемента управления и обработка события  
 В предыдущей процедуре продемонстрировано, как создать простейшую форму Windows Forms, скомпилировать и запустить ее.  В следующей процедуре будет показано, как создать и добавить в форму элемент управления и как обрабатывать событие для него.  Подробнее об элементах управления, которые можно добавить в форму Windows Forms, см. в разделе [Элементы управления Windows Forms](../../../docs/framework/winforms/controls/index.md).  
  
 Помимо понимания способов создания приложений Windows Forms, следует обладать общими знаниями о программировании на основе событий и способах обработки данных, введенных пользователем.  Подробнее см. в разделах [Creating Event Handlers in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md) и [Обработка введенных пользователем данных](../../../docs/framework/winforms/controls/handling-user-input.md).  
  
#### Объявление элемента управления типа "Кнопка" и обработка событий щелчка мышью для нее  
  
1.  Объявите элемент управления типа "Кнопка" с именем `button1`.  
  
2.  В конструкторе создайте кнопку и задайте ее свойства <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> и <xref:System.Windows.Forms.Control.Text%2A>.  
  
3.  Добавьте кнопку в форму.  
  
     В примере кода ниже показано, как объявить элемент управления типа "Кнопка".  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4.  Создайте метод для обработки события <xref:System.Windows.Forms.Control.Click> для кнопки.  
  
5.  В обработчике событий щелчка мышью выведите элемент управления <xref:System.Windows.Forms.MessageBox> с сообщением "Здравствуй, мир".  
  
     В примере кода ниже демонстрируется, как обрабатывать событие щелчка мышью для элемента управления типа "Кнопка".  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6.  Свяжите событие <xref:System.Windows.Forms.Control.Click> с созданным методом.  
  
     В примере кода ниже показано, как связать событие с методом.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7.  Скомпилируйте и запустите приложение, как описано в предыдущей процедуре.  
  
## Пример  
 В примере кода ниже полностью представлены все предыдущие процедуры.  
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## Компиляция кода  
  
-   Для компиляции кода следуйте инструкциям из предыдущей процедуры, описывающим, как скомпилировать и запустить приложение.  
  
## См. также  
 <xref:System.Windows.Forms.Form>   
 <xref:System.Windows.Forms.Control>   
 [Changing the Appearance of Windows Forms](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)   
 [Enhancing Windows Forms Applications](../../../docs/framework/winforms/advanced/index.md)   
 [Getting Started with Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)