---
title: "Руководство: Разработка простого элемента управления форм Windows Forms | Microsoft Docs"
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
  - "Control - класс, Windows Forms"
  - "элементы управления [Windows Forms]"
  - "пользовательские элементы управления [Windows Forms], создание простых элементов управления с использованием кода"
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Руководство: Разработка простого элемента управления форм Windows Forms
В этом разделе рассматриваются основные этапы разработки пользовательского элемента управления Windows Forms.  Простейший элемент управления, разработанный в этом пошаговом руководстве, позволяет изменять выравнивание своего свойства <xref:System.Windows.Forms.Control.Text%2A>.  Он не инициирует и не обрабатывает события.  
  
### Создание простого пользовательского элемента управления  
  
1.  Определите класс, унаследованный от класса <xref:System.Windows.Forms.Control?displayProperty=fullName>.  
  
    ```vb  
    Public Class FirstControl  
       Inherits Control  
  
    End Class  
    ```  
  
    ```csharp  
    public class FirstControl:Control{}  
    ```  
  
2.  Определите свойства.  \(Это необязательно, т.к. элемент управления наследует многие свойства от класса <xref:System.Windows.Forms.Control>, но для большинства пользовательских элементов управления обычно определяются дополнительные свойства.\) В следующем фрагменте кода определяется свойство с именем `TextAlignment` , которое используется`FirstControl` для форматирования значения свойства <xref:System.Windows.Forms.Control.Text%2A>, унаследованного от <xref:System.Windows.Forms.Control>.  Дополнительные сведения об определении свойств см. в разделе [Properties Overview](../Topic/Properties%20Overview.md).  
  
     [!code-csharp[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]  
  
     Когда задается свойство, изменяющее отрисовку элемента управления, следует вызвать метод <xref:System.Windows.Forms.Control.Invalidate%2A>, чтобы перерисовать элемент управления.  Метод <xref:System.Windows.Forms.Control.Invalidate%2A> определен в базовом классе <xref:System.Windows.Forms.Control>.  
  
3.  Переопределите защищенный метод <xref:System.Windows.Forms.Control.OnPaint%2A>, наследуемый от <xref:System.Windows.Forms.Control>, чтобы обеспечить логику отрисовки элемента управления.  Если не переопределить метод <xref:System.Windows.Forms.Control.OnPaint%2A>, элемент управления не сможет себя нарисовать.  В следующем фрагменте кода метод <xref:System.Windows.Forms.Control.OnPaint%2A> отображает значение свойства <xref:System.Windows.Forms.Control.Text%2A>, унаследованного от <xref:System.Windows.Forms.Control>, с выравниванием, определяемым значением поля `alignmentValue`.  
  
     [!code-csharp[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]  
  
4.  Задайте атрибуты для элемента управления.  Атрибуты позволят визуальному конструктору отображать элемент управления и, соответственно, его свойства и события в режиме разработки.  Следующий фрагмент кода применяет атрибуты для свойства `TextAlignment`.  В конструкторе, таком как Visual Studio, атрибут <xref:System.ComponentModel.CategoryAttribute.Category%2A> \(показанный во фрагменте кода\) позволяет свойству отображаться в соответствующей логической категории.  Атрибут <xref:System.ComponentModel.DescriptionAttribute.Description%2A> обеспечивает отображение строки описания внизу окна **Свойства**, если выбрано свойство `TextAlignment`.  Дополнительные сведения об атрибутах см. в разделе [Design\-Time Attributes for Components](../Topic/Design-Time%20Attributes%20for%20Components.md).  
  
     [!code-csharp[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]  
  
5.  Предоставьте ресурсы для элемента управления \(необязательное действие\).  Для элемента управления можно предоставить ресурс, такой как растровый рисунок, используя параметр компилятора \(`/res` для C\#\), чтобы упаковать ресурсы с элементом управления.  Во время выполнения ресурсы могут быть извлечены с помощью методов класса <xref:System.Resources.ResourceManager>.  Дополнительные сведения о создании и использовании ресурсов см. раздел [Ресурсы в приложениях для настольных систем](../../../../docs/framework/resources/index.md).  
  
6.  Выполните компиляцию и развертывание элемента управления.  Для компиляции и развертывания элемента управления `FirstControl,` выполните следующие шаги.  
  
    1.  Сохраните код следующего образца в исходном файле \(например, FirstControl.cs или FirstControl.vb\).  
  
    2.  Скомпилируйте исходный код в сборку и сохраните ее в каталоге приложения.  Для этого выполните следующую команду из каталога, содержащего исходный файл.  
  
        ```vb  
        vbc /t:library /out:[path to your application's directory]/CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll FirstControl.vb  
        ```  
  
        ```csharp  
        csc /t:library /out:[path to your application's directory]/CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll FirstControl.cs  
        ```  
  
         Параметр компилятора `/t:library` сообщает компилятору, что сборка, создаваемая пользователем, является библиотекой \(а не исполняемым файлом\).  Параметр `/out` задает путь и имя сборки.  Параметр `/r` задает имена сборок, на которые ссылается код.  В этом примере создается закрытая сборка, которую может использовать только приложение пользователя.  Следовательно, необходимо сохранить ее в каталоге приложения пользователя.  Дополнительные сведения об упаковке и развертывании элемента управления для распределения см. в разделе [Развертывание](../../../../docs/framework/deployment/net-framework-and-applications.md).  
  
 В следующем примере показан код модуля `FirstControl`.  Элемент управления помещается в пространство имен `CustomWinControls`.  Пространство имен обеспечивает логическое группирование связанных типов.  Можно создать элемент управления в новом или существующем пространстве имен.  В C\# объявление `using` \(в Visual Basic — `Imports`\) позволяет получать доступ к типам из пространства имен без использования полного имени типа.  В следующем примере объявление `using` разрешает доступ со стороны кода к классу <xref:System.Windows.Forms.Control> из <xref:System.Windows.Forms?displayProperty=fullName> как просто к <xref:System.Windows.Forms.Control> вместо использования полного имени <xref:System.Windows.Forms.Control?displayProperty=fullName>.  
  
 [!code-csharp[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
 [!code-vb[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]  
  
## Использование пользовательского элемента управления в форме  
 В следующем примере рассмотрена простая форма, использующая элемент управления `FirstControl`.  В нем создается три экземпляра `FirstControl`, все с разными значениями свойства `TextAlignment`.  
  
#### Компиляция и запуск примера  
  
1.  Сохраните код из следующего образца в исходном файле \(SimpleForm.cs или SimpleForms.vb\).  
  
2.  Скомпилируйте исходный код в исполняемую сборку, выполнив следующую команду из каталога, содержащего исходный файл.  
  
    ```vb  
    vbc /r:CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll SimpleForm.vb  
    ```  
  
    ```csharp  
    csc /r:CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll SimpleForm.cs  
    ```  
  
     CustomWinControls.dll — сборка, содержащая класс`FirstControl`.  Эта сборка должна находиться в том же каталоге, что и исходный файл для формы, которая к ней обращается \(SimpleForm.cs или SimpleForms.vb\).  
  
3.  Запустите на выполнение файл SimpleForm.exe с помощью следующей команды.  
  
    ```  
    SimpleForm  
    ```  
  
 [!code-csharp[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
 [!code-vb[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]  
  
## См. также  
 [Свойства элементов управления Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [События элементов управления Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)