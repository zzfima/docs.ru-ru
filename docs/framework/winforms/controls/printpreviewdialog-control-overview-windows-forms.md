---
title: Общие сведения об элементе управления PrintPreviewDialog (Windows Forms)
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: 670886956e1b348895862c117ccf9cf586bde8bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141218"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Общие сведения об элементе управления PrintPreviewDialog (Windows Forms)

Элемент управления Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> является предварительно настроенным диалоговым окном, используемым для отображения того, как [PrintDocument](printdocument-component-windows-forms.md) будет выглядеть при печати. Используйте его в приложении Windows в качестве простого решения вместо настройки собственного диалогового окна. Элемент управления содержит кнопки для печати, увеличения масштаба, отображения одной или нескольких страниц и закрытия диалогового окна.

## <a name="key-properties-and-methods"></a>Ключевые свойства и методы

Ключевым свойством элемента управления является <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, которое задает предварительный просмотр документа. Документ должен быть объектом <xref:System.Drawing.Printing.PrintDocument>. Чтобы отобразить диалоговое окно, необходимо вызвать его метод <xref:System.Windows.Forms.Form.ShowDialog%2A>. Сглаживание может сделать текст более плавным, но он также может замедлить отображение. чтобы использовать его, присвойте свойству <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> значение `true`.

Некоторые свойства доступны в <xref:System.Windows.Forms.PrintPreviewControl>, который содержит <xref:System.Windows.Forms.PrintPreviewDialog>. (Не нужно добавлять этот <xref:System.Windows.Forms.PrintPreviewControl> в форму; он автоматически содержится в <xref:System.Windows.Forms.PrintPreviewDialog> при добавлении диалогового окна в форму.) Примерами свойств, доступных в <xref:System.Windows.Forms.PrintPreviewControl>, являются свойства <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> и <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>, которые определяют количество страниц, отображаемых на элементе управления по горизонтали и вертикали. Доступ к свойству <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> можно получить как `PrintPreviewDialog1.PrintPreviewControl.Columns` в Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` в C#визуальном элементе или `printPreviewDialog1->PrintPreviewControl->Columns` C++в Visual.

## <a name="printpreviewdialog-performance"></a>Производительность PrintPreviewDialog

При выполнении следующих условий элемент управления <xref:System.Windows.Forms.PrintPreviewDialog> инициализируется очень медленно:

- Используется сетевой принтер.
- Параметры пользователя для этого принтера, такие как дуплексные параметры, изменяются.

Для приложений, выполняющихся на .NET Framework 4.5.2, можно добавить следующий ключ в раздел \<appSettings > файла конфигурации, чтобы повысить производительность при инициализации элемента управления <xref:System.Windows.Forms.PrintPreviewDialog>.

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

Если для ключа `EnablePrintPreviewOptimization` задано любое другое значение или отсутствует ключ, оптимизация не применяется.

Для приложений, выполняющихся на .NET Framework 4,6 или более поздних версий, можно добавить следующий параметр в элемент [\<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [\<среды выполнения >](../../configure-apps/file-schema/runtime/index.md) файла конфигурации приложения:

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

Если параметр отсутствует или для него задано любое другое значение, оптимизация не применяется.

Если для изменения параметров принтера используется событие <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings>, производительность элемента управления <xref:System.Windows.Forms.PrintPreviewDialog> не повысится, даже если установлен параметр конфигурации оптимизации.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [Общие сведения об элементе управления PrintPreviewControl](printpreviewcontrol-control-overview-windows-forms.md)
- [Элемент управления PrintPreviewDialog](printpreviewdialog-control-windows-forms.md)
- [Элементы управления и компоненты диалоговых окон](dialog-box-controls-and-components-windows-forms.md)
