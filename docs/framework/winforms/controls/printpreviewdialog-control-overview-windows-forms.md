---
title: "Общие сведения об элементе управления PrintPreviewDialog (Windows Forms)"
ms.custom: 
ms.date: 01/08/2018
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewDialog
helpviewer_keywords: PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1228a3cf39ea412cde341c4c4b8b83e0ab2f0299
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2018
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Обзор управления PrintPreviewDialog (Windows Forms)
Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> управления является стандартным диалоговым окном, используемый для отображения как [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) будет выглядеть при печати. Он используется в приложении Windows в качестве простого решения вместо настройки собственного диалогового. Элемент управления содержит кнопки для печати, увеличения масштаба, отображения одной или нескольких страниц и закрытия диалогового окна.  
  
## <a name="key-properties-and-methods"></a>Ключевые свойства и методы  
 Ключевое свойство элемента управления <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, который задает документ для предварительного просмотра. Документ должен быть <xref:System.Drawing.Printing.PrintDocument> объекта. Чтобы открыть диалоговое окно, необходимо вызвать его <xref:System.Windows.Forms.Form.ShowDialog%2A> метод. Сглаживание можно увеличить гладкую текст, но оно может привести к замедлению отображения; Чтобы использовать его, установите <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> свойства `true`.  
  
 Некоторые свойства доступны через <xref:System.Windows.Forms.PrintPreviewControl> , <xref:System.Windows.Forms.PrintPreviewDialog> содержит. (Необходимо добавить это <xref:System.Windows.Forms.PrintPreviewControl> форме; он автоматически внутри <xref:System.Windows.Forms.PrintPreviewDialog> при добавлении диалогового окна в форму.) Примеры свойств, доступных через <xref:System.Windows.Forms.PrintPreviewControl> , <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> и <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> свойства, которые определяют число страниц, отображаемых по горизонтали и вертикали в элементе управления. Вы можете получить доступ к <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> свойство как `PrintPreviewDialog1.PrintPreviewControl.Columns` в [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` в [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], или `printPreviewDialog1->PrintPreviewControl->Columns` в [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].  
  
## <a name="printpreviewdialog-performance"></a>Производительность PrintPreviewDialog

При следующих условиях <xref:System.Windows.Forms.PrintPreviewDialog> элемент управления инициализирует очень медленно:

- Используется сетевого принтера.
- Пользовательские параметры для этого принтера, например дуплексного параметры будут изменены.
  
Для приложений, выполняющихся в .NET Framework 4.5.2, можно добавить следующий раздел, чтобы \<appSettings > раздел файла конфигурации для повышения производительности <xref:System.Windows.Forms.PrintPreviewDialog> управления инициализации:

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
Если `EnablePrintPreviewOptimization` ключа задано любое другое значение, или если параметр не указан, оптимизация не применяется.

Для приложений, выполняющихся в .NET Framework 4.6 или более поздней версии, можно добавить следующий параметр для [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) элемент в [ \<среды выполнения >](../../configure-apps/file-schema/runtime/index.md) раздел файла конфигурации приложения:

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
Если параметр не указан или если оно задано любое другое значение, оптимизация не применяется. 

Если вы используете <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> событий для изменения параметров принтера, производительность <xref:System.Windows.Forms.PrintPreviewDialog> управления не улучшит, даже если задан параметр конфигурации оптимизации.  

## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [Общие сведения об элементе управления PrintPreviewControl](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [Элемент управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Элементы управления и компоненты диалоговых окон](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
