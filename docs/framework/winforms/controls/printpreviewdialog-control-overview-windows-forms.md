---
title: Общие сведения об элементе управления PrintPreviewDialog (Windows Forms)
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0946220017fb78775f045bb225d84ea95aecd06b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538341"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="55e85-102">Обзор управления PrintPreviewDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="55e85-102">PrintPreviewDialog control overview (Windows Forms)</span></span>
<span data-ttu-id="55e85-103">Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> управления является стандартным диалоговым окном, используемый для отображения как [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) будет выглядеть при печати.</span><span class="sxs-lookup"><span data-stu-id="55e85-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="55e85-104">Он используется в приложении Windows в качестве простого решения вместо настройки собственного диалогового.</span><span class="sxs-lookup"><span data-stu-id="55e85-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="55e85-105">Элемент управления содержит кнопки для печати, увеличения масштаба, отображения одной или нескольких страниц и закрытия диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="55e85-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="55e85-106">Ключевые свойства и методы</span><span class="sxs-lookup"><span data-stu-id="55e85-106">Key properties and methods</span></span>  
 <span data-ttu-id="55e85-107">Ключевое свойство элемента управления <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, который задает документ для предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="55e85-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="55e85-108">Документ должен быть <xref:System.Drawing.Printing.PrintDocument> объекта.</span><span class="sxs-lookup"><span data-stu-id="55e85-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="55e85-109">Чтобы открыть диалоговое окно, необходимо вызвать его <xref:System.Windows.Forms.Form.ShowDialog%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="55e85-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="55e85-110">Сглаживание можно увеличить гладкую текст, но оно может привести к замедлению отображения; Чтобы использовать его, установите <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="55e85-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="55e85-111">Некоторые свойства доступны через <xref:System.Windows.Forms.PrintPreviewControl> , <xref:System.Windows.Forms.PrintPreviewDialog> содержит.</span><span class="sxs-lookup"><span data-stu-id="55e85-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="55e85-112">(Необходимо добавить это <xref:System.Windows.Forms.PrintPreviewControl> форме; он автоматически внутри <xref:System.Windows.Forms.PrintPreviewDialog> при добавлении диалогового окна в форму.) Примеры свойств, доступных через <xref:System.Windows.Forms.PrintPreviewControl> , <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> и <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> свойства, которые определяют число страниц, отображаемых по горизонтали и вертикали в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="55e85-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="55e85-113">Вы можете получить доступ к <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> свойство как `PrintPreviewDialog1.PrintPreviewControl.Columns` в Visual Basic `printPreviewDialog1.PrintPreviewControl.Columns` в Visual C# или `printPreviewDialog1->PrintPreviewControl->Columns` в [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55e85-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span></span>  
  
## <a name="printpreviewdialog-performance"></a><span data-ttu-id="55e85-114">Производительность PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="55e85-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="55e85-115">При следующих условиях <xref:System.Windows.Forms.PrintPreviewDialog> элемент управления инициализирует очень медленно:</span><span class="sxs-lookup"><span data-stu-id="55e85-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="55e85-116">Используется сетевого принтера.</span><span class="sxs-lookup"><span data-stu-id="55e85-116">A network printer is used.</span></span>
- <span data-ttu-id="55e85-117">Пользовательские параметры для этого принтера, например дуплексного параметры будут изменены.</span><span class="sxs-lookup"><span data-stu-id="55e85-117">User preferences for this printer, such as duplex settings, are modified.</span></span>
  
<span data-ttu-id="55e85-118">Для приложений, выполняющихся в .NET Framework 4.5.2, можно добавить следующий раздел, чтобы \<appSettings > раздел файла конфигурации для повышения производительности <xref:System.Windows.Forms.PrintPreviewDialog> управления инициализации:</span><span class="sxs-lookup"><span data-stu-id="55e85-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
<span data-ttu-id="55e85-119">Если `EnablePrintPreviewOptimization` ключа задано любое другое значение, или если параметр не указан, оптимизация не применяется.</span><span class="sxs-lookup"><span data-stu-id="55e85-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="55e85-120">Для приложений, выполняющихся в .NET Framework 4.6 или более поздней версии, можно добавить следующий параметр для [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) элемент в [ \<среды выполнения >](../../configure-apps/file-schema/runtime/index.md) раздел файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="55e85-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
<span data-ttu-id="55e85-121">Если параметр не указан или если оно задано любое другое значение, оптимизация не применяется.</span><span class="sxs-lookup"><span data-stu-id="55e85-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span> 

<span data-ttu-id="55e85-122">Если вы используете <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> событий для изменения параметров принтера, производительность <xref:System.Windows.Forms.PrintPreviewDialog> управления не улучшит, даже если задан параметр конфигурации оптимизации.</span><span class="sxs-lookup"><span data-stu-id="55e85-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>  

## <a name="see-also"></a><span data-ttu-id="55e85-123">См. также</span><span class="sxs-lookup"><span data-stu-id="55e85-123">See also</span></span>  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [<span data-ttu-id="55e85-124">Общие сведения об элементе управления PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="55e85-124">PrintPreviewControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="55e85-125">Элемент управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="55e85-125">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="55e85-126">Элементы управления и компоненты диалоговых окон</span><span class="sxs-lookup"><span data-stu-id="55e85-126">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
