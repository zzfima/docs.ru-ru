---
title: Создание приложения Windows Forms из командной строки
titleSuffix: ''
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
ms.openlocfilehash: 7bd3add526a6b60d628b05d46eca22ce407c36b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181987"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a>Как: Создать приложение Windows Forms из командной строки

В процедурах ниже описаны основные шаги, которые необходимо выполнить для создания и запуска приложения Windows Forms из командной строки. Visual Studio предлагает расширенную поддержку этих процедур.  Также смотрите [Пошагово: Хостинг Управления формами Windows в WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).
  
## <a name="procedure"></a>Процедура  
  
#### <a name="to-create-the-form"></a>Создание формы  
  
1. В пустом файле кода `Imports` `using` введите следующие или операторы:  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. Объявить класс, названный, `Form1` который наследует от класса формы:
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. Создайте безпаралисастого конструктора для. `Form1`
  
     В следующий процедуре будет добавлен дополнительный код конструктора.
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. Добавьте в класс метод `Main`.
  
    1. Примените <xref:System.STAThreadAttribute> метод `Main` C,, чтобы указать, что ваше приложение Windows Forms является однопоточной квартирой. (Атрибут не является необходимым в Visual Basic, так как Windows формирует приложения, разработанные с Visual Basic, используют однопонищенную модель апартаментов по умолчанию.)  
  
    2. Вызов <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> для применения стилей операционной системы в приложении.  
  
    3. Создайте экземпляр формы и запустите его.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a>Компиляция и запуск приложения  
  
1. В командной строке .NET Framework перейдите к папке, в которой содержится класс `Form1`.  
  
2. Скомпилируйте форму.  
  
    - Если вы используете C q, введите:`csc form1.cs`  
  
         `-or-`  
  
    - Если вы используете Visual Basic, введите:`vbc form1.vb`  
  
3. В командной строке введите следующий текст: `Form1.exe`.  
  
## <a name="adding-a-control-and-handling-an-event"></a>Добавление элемента управления и обработки события

В предыдущей процедуре продемонстрировано, как создать простейшую форму Windows Forms, скомпилировать и запустить ее. В следующей процедуре будет показано, как создать и добавить в форму элемент управления и как обрабатывать событие для него. Для получения дополнительной информации об элементах [Windows Forms Controls](./controls/index.md)управления, которые можно добавить в формы Windows, см.
  
 Помимо понимания способов создания приложений Windows Forms, следует обладать общими знаниями о программировании на основе событий и способах обработки данных, введенных пользователем. Для получения дополнительной информации [Handling User Input](./controls/handling-user-input.md) см. [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md)  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a>Объявление элемента управления типа "Кнопка" и обработка событий щелчка мышью для нее  
  
1. Объявите элемент управления типа "Кнопка" с именем `button1`.  
  
2. В конструкторе создайте кнопку и задайте ее свойства <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> и <xref:System.Windows.Forms.Control.Text%2A>.  
  
3. Добавьте кнопку в форму.  
  
     Следующий пример кода показывает, как объявить управление кнопкой:
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. Создайте метод для обработки события <xref:System.Windows.Forms.Control.Click> для кнопки.  
  
5. В обработчике событий щелчка мышью выведите элемент управления <xref:System.Windows.Forms.MessageBox> с сообщением "Здравствуй, мир".  
  
     Следующий пример кода демонстрирует, как обрабатывать событие нажатия кнопки:
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. Свяжите событие <xref:System.Windows.Forms.Control.Click> с созданным методом.  
  
     В примере кода ниже показано, как связать событие с методом.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. Скомпилируйте и запустите приложение, как описано в предыдущей процедуре.  
  
## <a name="example"></a>Пример  

Следующий пример кода является полным примером из предыдущих процедур:
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [Изменение внешнего вида Windows Forms](changing-the-appearance-of-windows-forms.md)
- [Усовершенствование приложений Windows Forms](./advanced/index.md)
- [Приступая к работе с Windows Forms](getting-started-with-windows-forms.md)
