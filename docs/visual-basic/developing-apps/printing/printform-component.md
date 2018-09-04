---
title: Компонент PrintForm (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- PrintForm component [Visual Basic]
ms.assetid: 03de98b8-b54c-4764-91d7-83c64e974750
ms.openlocfilehash: 879d31c5a572689d84af6b2e46f3d33e1a8841c8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43534249"
---
# <a name="printform-component-visual-basic"></a>Компонент PrintForm (Visual Basic)
<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Компонент для Visual Basic позволяет напечатать изображение формы Windows во время выполнения. Его поведение заменяет поведение метода `PrintForm` в более ранних версиях Visual Basic.  
  
 Элементы управления PowerPack больше не включены в Visual Studio, но их можно скачать [центра загрузки](https://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
## <a name="printform-component-overview"></a>Обзор компонента PrintForm  
 Распространенной ситуацией, связанной с формами Windows Forms, является создание формы с форматированием, которое походит на бумажную форму или отчет, а затем печать изображения формы. Также для этого можно использовать компонент <xref:System.Drawing.Printing.PrintDocument> , хотя это требует большого объема кода. Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> позволяет вывести изображение формы для печати на принтер, в окно предварительного просмотра печати или в файл без использования компонента <xref:System.Drawing.Printing.PrintDocument> .  
  
 Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> расположен на вкладке **Visual Basic PowerPacks** **панели элементов**. При перетаскивании в форму он отображается в небольшой области компонентов, расположенной под нижней границей формы. Для выбранного компонента определяющие его поведение свойства можно задать в окне **Свойства** . Все эти свойства можно также задать в коде. Можно также создать экземпляр компонента <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> в коде без добавления компонента во время разработки.  
  
 При печати формы печатается все содержимое клиентской области формы. Это включает в себя все элементы управления, а также любой текст и графику. По умолчанию заголовок, полосы прокрутки и границы формы не печатаются. По умолчанию компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> печатает только видимую часть формы. Например, если пользователь изменяет размер формы во время выполнения, будут напечатаны только видимые элементы управления и графика.  
  
 Принтер по умолчанию, используемый компонентом <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> , определяется параметрами панели управления операционной системы.  
  
 После запуска печати отображается стандартное диалоговое окно печати <xref:System.Drawing.Printing.PrintDocument> . Это диалоговое окно позволяет пользователям отменить задание печати.  
  
### <a name="key-methods-properties-and-events"></a>Ключевые методы, свойства и события  
 Основной метод компонента <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> — метод <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> , который выводит изображение формы на принтер, в окно предварительного просмотра печати или в файл. Существуют две версии метода <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> .  
  
-   Базовая версия без параметров: `Print()`  
  
-   Перегруженная версия с параметрами, задающими режим печати: `Print(printForm As Form, printFormOption As PrintOption)`  
  
     Параметр `PrintOption` перегруженного метода определяет базовую реализацию, используемую для печати формы, указывает, печатаются ли заголовок формы, полосы прокрутки и границы или прокручиваемые области формы.  
  
 Свойство <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> является основным свойством компонента <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> . Это свойство определяет, отправляются ли выходные данные на принтер, отображаются ли в окне предварительного просмотра или сохраняются в виде EPS-файла. Если для свойства <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> задано значение <xref:System.Drawing.Printing.PrintAction.PrintToFile>, свойство <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> указывает путь и имя файла.  
  
 Свойство <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrinterSettings%2A> предоставляет доступ к базовому объекту <xref:System.Drawing.Printing.PrintDocument.PrinterSettings%2A> , который позволяет задать такие параметры, как используемый принтер и количество печатаемых копий. Можно также запрашивать возможности принтера, например цветность или двухстороннюю печать. Это свойство не отображается в окне **Свойства** ; доступ к нему может осуществляться только из кода.  
  
 Свойство <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Form%2A> используется для указания формы для печати при программном вызове компонента <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> . Если компонент добавляется в форму во время разработки, эта форма используется по умолчанию.  
  
 К основным событиям компонента <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> относятся следующие.  
  
-   Событие<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.BeginPrint> . Происходит при вызове метода <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> и перед печатью первой страницы документа.  
  
-   Событие<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.EndPrint> . Происходит после вывода на печать последней страницы.  
  
-   Событие<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.QueryPageSettings> . Происходит непосредственно перед печатью каждой страницы.  
  
### <a name="remarks"></a>Примечания  
 Если форма содержит текст или графику, созданную методами <xref:System.Drawing.Graphics> , используйте базовый метод <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> (`Print()`) для печати. Графика может не отображаться в некоторых операционных системах при использовании перегруженного метода <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A> .  
  
 Если ширина формы превышает ширину бумаги в принтере, правая часть формы может быть обрезана. При разработке форм для печати убедитесь, что они умещаются на листе стандартного формата.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется типичное использование компонента <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> .  
  
```  
' Visual Basic.  
Dim pf As New PrintForm  
pf.Form = Me  
pf.PrintAction = PrintToPrinter  
pf.Print()  
```  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 [Практическое руководство. Печать формы с помощью компонента PrintForm](../../../visual-basic/developing-apps/printing/how-to-print-a-form-by-using-the-printform-component.md)  
 [Практическое руководство. Печать клиентской области формы](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [Практическое руководство. Печать клиентской и неклиентской области формы](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)  
 [Практическое руководство. Печать прокручиваемой формы](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
