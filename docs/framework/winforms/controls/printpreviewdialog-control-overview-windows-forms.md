---
title: Общие сведения об элементе управления PrintPreviewDialog
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: 6fb971493336cda1e04c720dd09147e650918c3a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741407"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="4caaa-102">Общие сведения об элементе управления PrintPreviewDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4caaa-102">PrintPreviewDialog control overview (Windows Forms)</span></span>

<span data-ttu-id="4caaa-103">Элемент управления Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> является предварительно настроенным диалоговым окном, используемым для отображения того, как [PrintDocument](printdocument-component-windows-forms.md) будет выглядеть при печати.</span><span class="sxs-lookup"><span data-stu-id="4caaa-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="4caaa-104">Используйте его в приложении Windows в качестве простого решения вместо настройки собственного диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="4caaa-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="4caaa-105">Элемент управления содержит кнопки для печати, увеличения масштаба, отображения одной или нескольких страниц и закрытия диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="4caaa-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="4caaa-106">Ключевые свойства и методы</span><span class="sxs-lookup"><span data-stu-id="4caaa-106">Key properties and methods</span></span>

<span data-ttu-id="4caaa-107">Ключевым свойством элемента управления является <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, которое задает предварительный просмотр документа.</span><span class="sxs-lookup"><span data-stu-id="4caaa-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="4caaa-108">Документ должен быть объектом <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="4caaa-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="4caaa-109">Чтобы отобразить диалоговое окно, необходимо вызвать его метод <xref:System.Windows.Forms.Form.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="4caaa-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="4caaa-110">Сглаживание может сделать текст более плавным, но он также может замедлить отображение. чтобы использовать его, присвойте свойству <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="4caaa-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>

<span data-ttu-id="4caaa-111">Некоторые свойства доступны в <xref:System.Windows.Forms.PrintPreviewControl>, который содержит <xref:System.Windows.Forms.PrintPreviewDialog>.</span><span class="sxs-lookup"><span data-stu-id="4caaa-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="4caaa-112">(Не нужно добавлять этот <xref:System.Windows.Forms.PrintPreviewControl> в форму; он автоматически содержится в <xref:System.Windows.Forms.PrintPreviewDialog> при добавлении диалогового окна в форму.) Примерами свойств, доступных в <xref:System.Windows.Forms.PrintPreviewControl>, являются свойства <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> и <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>, которые определяют количество страниц, отображаемых на элементе управления по горизонтали и вертикали.</span><span class="sxs-lookup"><span data-stu-id="4caaa-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="4caaa-113">Доступ к свойству <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> можно получить как `PrintPreviewDialog1.PrintPreviewControl.Columns` в Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` в C#визуальном элементе или `printPreviewDialog1->PrintPreviewControl->Columns` C++в Visual.</span><span class="sxs-lookup"><span data-stu-id="4caaa-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span></span>

## <a name="printpreviewdialog-performance"></a><span data-ttu-id="4caaa-114">Производительность PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="4caaa-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="4caaa-115">При выполнении следующих условий элемент управления <xref:System.Windows.Forms.PrintPreviewDialog> инициализируется очень медленно:</span><span class="sxs-lookup"><span data-stu-id="4caaa-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="4caaa-116">Используется сетевой принтер.</span><span class="sxs-lookup"><span data-stu-id="4caaa-116">A network printer is used.</span></span>
- <span data-ttu-id="4caaa-117">Параметры пользователя для этого принтера, такие как дуплексные параметры, изменяются.</span><span class="sxs-lookup"><span data-stu-id="4caaa-117">User preferences for this printer, such as duplex settings, are modified.</span></span>

<span data-ttu-id="4caaa-118">Для приложений, выполняющихся на .NET Framework 4.5.2, можно добавить следующий ключ в раздел \<appSettings > файла конфигурации, чтобы повысить производительность при инициализации элемента управления <xref:System.Windows.Forms.PrintPreviewDialog>.</span><span class="sxs-lookup"><span data-stu-id="4caaa-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

<span data-ttu-id="4caaa-119">Если для ключа `EnablePrintPreviewOptimization` задано любое другое значение или отсутствует ключ, оптимизация не применяется.</span><span class="sxs-lookup"><span data-stu-id="4caaa-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="4caaa-120">Для приложений, выполняющихся на .NET Framework 4,6 или более поздних версий, можно добавить следующий параметр в элемент [\<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [\<среды выполнения >](../../configure-apps/file-schema/runtime/index.md) файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="4caaa-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

<span data-ttu-id="4caaa-121">Если параметр отсутствует или для него задано любое другое значение, оптимизация не применяется.</span><span class="sxs-lookup"><span data-stu-id="4caaa-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span>

<span data-ttu-id="4caaa-122">Если для изменения параметров принтера используется событие <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings>, производительность элемента управления <xref:System.Windows.Forms.PrintPreviewDialog> не повысится, даже если установлен параметр конфигурации оптимизации.</span><span class="sxs-lookup"><span data-stu-id="4caaa-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>

## <a name="see-also"></a><span data-ttu-id="4caaa-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4caaa-123">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="4caaa-124">Общие сведения об элементе управления PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="4caaa-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="4caaa-125">Элемент управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="4caaa-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="4caaa-126">Элементы управления и компоненты диалоговых окон</span><span class="sxs-lookup"><span data-stu-id="4caaa-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
