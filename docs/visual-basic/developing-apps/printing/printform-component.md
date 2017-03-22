---
title: "Компонент PrintForm (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- PrintForm component [Visual Basic]
ms.assetid: 03de98b8-b54c-4764-91d7-83c64e974750
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f0c51ef0131c874ed33af7a19f9145a790d14ade
ms.lasthandoff: 03/13/2017

---
# <a name="printform-component-visual-basic"></a>Компонент PrintForm (Visual Basic)
<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Компонент для [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] позволяет напечатать изображение формы Windows Forms во время выполнения.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Его поведение заменяет поведение метода `PrintForm` в более ранних версиях Visual Basic.  
  
 Элементы управления PowerPack больше не включены в Visual Studio, но их можно скачать в [Центре загрузки](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
## <a name="printform-component-overview"></a>Обзор компонента PrintForm  
 Распространенной ситуацией, связанной с формами Windows Forms, является создание формы с форматированием, которое походит на бумажную форму или отчет, а затем печать изображения формы. Хотя можно использовать <xref:System.Drawing.Printing.PrintDocument>компонента, чтобы сделать это, требует большого объема кода.</xref:System.Drawing.Printing.PrintDocument> <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Компонент позволяет напечатать изображение формы на принтере, окно предварительного просмотра печати или в файл без использования <xref:System.Drawing.Printing.PrintDocument>компонента.</xref:System.Drawing.Printing.PrintDocument> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Компонент расположен на **Visual Basic PowerPacks** вкладке **элементов**.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> При перетаскивании в форму он отображается в небольшой области компонентов, расположенной под нижней границей формы. Для выбранного компонента определяющие его поведение свойства можно задать в окне **Свойства** . Все эти свойства можно также задать в коде. Можно также создать экземпляр <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонента в коде без добавления компонента во время разработки.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 При печати формы печатается все содержимое клиентской области формы. Это включает в себя все элементы управления, а также любой текст и графику. По умолчанию заголовок, полосы прокрутки и границы формы не печатаются. По умолчанию <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонент выводит видимой части формы.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Например, если пользователь изменяет размер формы во время выполнения, будут напечатаны только видимые элементы управления и графика.  
  
 Принтер по умолчанию, используемые <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонента определяется настройками панели управления операционной системы.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 После запуска печати стандартного <xref:System.Drawing.Printing.PrintDocument>отображается диалоговое окно печати.</xref:System.Drawing.Printing.PrintDocument> Это диалоговое окно позволяет пользователям отменить задание печати.  
  
### <a name="key-methods-properties-and-events"></a>Ключевые методы, свойства и события  
 Основным методом <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>метод, который выводит изображение формы на принтер, окно предварительного просмотра печати или файл.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Существует две версии <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>метод:</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
  
-   Базовая версия без параметров:`Print()`  
  
-   Перегруженная версия с параметрами, задающими режим печати:`Print(printForm As Form, printFormOption As PrintOption)`  
  
     Параметр `PrintOption` перегруженного метода определяет базовую реализацию, используемую для печати формы, указывает, печатаются ли заголовок формы, полосы прокрутки и границы или прокручиваемые области формы.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>Свойство является ключевым свойством <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонента.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> Это свойство определяет, отправляются ли выходные данные на принтер, отображаются ли в окне предварительного просмотра или сохраняются в виде EPS-файла. Если <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>свойству <xref:System.Drawing.Printing.PrintAction>, <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>свойство указывает путь и имя файла.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> </xref:System.Drawing.Printing.PrintAction> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A>Свойство предоставляет доступ к основной <xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A>объект, позволяющий задать такие параметры, как принтер и число копий печать.</xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A> Можно также запрашивать возможности принтера, например цветность или двухстороннюю печать. Это свойство не отображается в окне **Свойства** ; доступ к нему может осуществляться только из кода.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A>Свойство используется для указания формы для печати при вызове <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонента программным способом.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> </xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A> Если компонент добавляется в форму во время разработки, эта форма используется по умолчанию.  
  
 Основные события для <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонентов входят следующие:</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint>событие.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint> Происходит при <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>вызывается метод и перед первой страницы документа печатается.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint>событие.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint> Происходит после вывода на печать последней страницы.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings>событие.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings> Происходит непосредственно перед печатью каждой страницы.  
  
### <a name="remarks"></a>Примечания  
 Если форма содержит текст или рисунки, изображенные с <xref:System.Drawing.Graphics>методов, использовать базовую <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>(`Print()`) метод, чтобы распечатать.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> </xref:System.Drawing.Graphics> Графика может не отображаться в некоторых операционных системах при перегруженных <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>используется метод.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
  
 Если ширина формы превышает ширину бумаги в принтере, правая часть формы может быть обрезана. При разработке форм для печати убедитесь, что они умещаются на листе стандартного формата.  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование общих <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонента.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
```  
' Visual Basic.  
Dim pf As New PrintForm  
pf.Form = Me  
pf.PrintAction = PrintToPrinter  
pf.Print()  
```  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A></xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A></xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>   
 [Практическое руководство: печать формы с помощью компонента PrintForm](../../../visual-basic/developing-apps/printing/how-to-print-a-form-by-using-the-printform-component.md)   
 [Практическое руководство: Печать клиентской области формы](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)   
 [Практическое руководство: Печать клиентской и неклиентской области формы](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)   
 [Практическое руководство. Печать прокручиваемой формы](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
