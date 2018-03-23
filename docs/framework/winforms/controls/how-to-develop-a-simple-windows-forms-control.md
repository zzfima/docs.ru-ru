---
title: 'Руководство: Разработка простого элемента управления форм Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ab7fced9237cad3de30d417770f6f1d7f7e7ed6a
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a>Руководство: Разработка простого элемента управления форм Windows Forms
В этом разделе рассматриваются основные этапы создания пользовательского элемента управления Windows Forms. Простой элемент управления, разработанный в этом примере разрешает выравнивание его <xref:System.Windows.Forms.Control.Text%2A> значение изменяемого свойства. Он не вызывает и не обрабатывает события.  
  
### <a name="to-create-a-simple-custom-control"></a>Создание простого пользовательского элемента управления  
  
1.  Определите класс, производный от класса <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
    ```vb  
    Public Class FirstControl  
       Inherits Control  
  
    End Class  
    ```  
  
    ```csharp  
    public class FirstControl:Control{}  
    ```  
  
2.  Определите свойства. (Вам не требуются для определения свойств, так как элемент управления наследует многие свойства от <xref:System.Windows.Forms.Control> класс, но большинство пользовательских элементов управления обычно определяются дополнительные свойства.) В следующем фрагменте кода определяется свойство с именем `TextAlignment` , `FirstControl` использует для форматирования значения <xref:System.Windows.Forms.Control.Text%2A> свойство унаследовано от <xref:System.Windows.Forms.Control>. Дополнительные сведения об определении свойств см. в разделе [Общие сведения о свойствах](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52).  
  
     [!code-csharp[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]  
  
     Если задано свойство, которое изменяет визуальное представление элемента управления, необходимо вызвать <xref:System.Windows.Forms.Control.Invalidate%2A> метод необходимости перерисовки элемента управления. <xref:System.Windows.Forms.Control.Invalidate%2A> определен в базовом классе <xref:System.Windows.Forms.Control>.  
  
3.  Переопределите защищенный <xref:System.Windows.Forms.Control.OnPaint%2A> метод наследуется от <xref:System.Windows.Forms.Control> для предоставления логики отрисовки для элемента управления. Если не следует переопределять <xref:System.Windows.Forms.Control.OnPaint%2A>, ваш элемент управления не сможет себя нарисовать. В следующем фрагменте кода <xref:System.Windows.Forms.Control.OnPaint%2A> метод выводит <xref:System.Windows.Forms.Control.Text%2A> свойство унаследовано от <xref:System.Windows.Forms.Control> с выравниванием, определяемым значением `alignmentValue` поля.  
  
     [!code-csharp[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]  
  
4.  Укажите атрибуты для своего элемента управления. Атрибуты позволяют визуальному конструктору адекватно отображать ваш элемент управления, а также его свойства и события во время разработки. Код в следующем фрагменте применяет атрибуты к свойству `TextAlignment`. В конструкторе, например Visual Studio <xref:System.ComponentModel.CategoryAttribute.Category%2A> атрибут (показано в приведенном фрагменте кода) позволяет свойству отображаться в логические категории. <xref:System.ComponentModel.DescriptionAttribute.Description%2A> Атрибут вызывает строку описания, отображаемый в нижней части **свойства** окна при `TextAlignment` выбрано свойство. Дополнительные сведения об атрибутах см. в разделе [Атрибуты времени разработки для компонентов](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3).  
  
     [!code-csharp[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]  
  
5.  (Необязательно.) Предоставьте элементу управления ресурсы. Чтобы предоставить элементу управления ресурс, такой как растровое изображение, можно использовать параметр компилятора (`/res` для C#), позволяющий упаковать ресурсы с элементом управления. Во время выполнения ресурса можно получить с помощью методов <xref:System.Resources.ResourceManager> класса. Более подробную информацию о создании и использовании ресурсов см. в разделе [Ресурсы в приложениях для настольных систем](../../../../docs/framework/resources/index.md).  
  
6.  Скомпилируйте и разверните элемент управления. Чтобы скомпилировать и развернуть `FirstControl,`, выполните следующие действия.  
  
    1.  Сохраните код из представленного ниже примера в исходный файл (например, FirstControl.cs или FirstControl.vb).  
  
    2.  Скомпилируйте исходный код в сборку и сохраните его в каталог приложения. Для этого выполните следующую команду из каталога, содержащего исходный файл.  
  
        ```console  
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb  
        ```  
  
        ```console 
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs  
        ```  
  
         Параметр компилятора `/t:library` сообщает компилятору, что создаваемая сборка является библиотекой (а не исполняемым файлом). Параметр `/out` определяет путь и имя сборки. Параметр `/r` определяет имена сборок, на которые ссылается код. В этом примере создается закрытая сборка, которую могут использовать только ваши приложения. Это значит, что сохранить ее в каталог приложения нельзя. Дополнительные сведения об упаковке и развертывании элемента управления, который нужно распределить, см. в разделе [Развертывание](../../../../docs/framework/deployment/index.md).  
  
 В следующем примере показан код для `FirstControl`. Элемент управления помещается в пространство имен `CustomWinControls`. Это пространство имен обеспечивает логическое группирование связанных типов. Элемент управления можно создавать в новом или в уже существующем пространстве имен. В C# объявление `using` (в Visual Basic `Imports`) обеспечивает доступ к типам из пространства имен без использования полного имени типа. В следующем примере `using` объявление позволяет коду доступ к классу <xref:System.Windows.Forms.Control> из <xref:System.Windows.Forms?displayProperty=nameWithType> просто <xref:System.Windows.Forms.Control> вместо того чтобы использовать полное доменное имя <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
 [!code-csharp[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
 [!code-vb[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]  
  
## <a name="using-the-custom-control-on-a-form"></a>Использование пользовательского элемента управления в форме  
 В следующем примере показана простая форма с использованием `FirstControl`. Она создает три экземпляра `FirstControl` с разными значениями свойства `TextAlignment`.  
  
#### <a name="to-compile-and-run-this-sample"></a>Компиляция и выполнение примера  
  
1.  Сохраните код в следующем примере в исходный файл (SimpleForm.cs или SimpleForms.vb).  
  
2.  Скомпилируйте исходный код в исполняемую сборку, выполнив следующую команду из каталога, содержащего исходный файл.  
  
    ```console  
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb  
    ```  
  
    ```console 
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs  
    ```  
  
     CustomWinControls.dll — это сборка, которая содержит класс `FirstControl`. Эта сборка должна находиться в том же каталоге, что и исходный файл для формы, которая к ней обращается (SimpleForm.cs или SimpleForms.vb).  
  
3.  Выполните файла SimpleForm.exe с помощью следующей команды.  
  
    ```console
    SimpleForm  
    ```  
  
 [!code-csharp[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
 [!code-vb[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]  
  
## <a name="see-also"></a>См. также  
 [Свойства элементов управления Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [События элементов управления Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)
