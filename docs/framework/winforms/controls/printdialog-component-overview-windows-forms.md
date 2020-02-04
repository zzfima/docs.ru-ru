---
title: Общие сведения о компоненте PrintDialog
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728676"
---
# <a name="printdialog-component-overview-windows-forms"></a>Общие сведения о компоненте PrintDialog (Windows Forms)

Компонент Windows Forms [PrintDialog](printdialog-component-windows-forms.md) — это предварительно настроенное диалоговое окно, используемое для выбора принтера, выбора страниц для печати и определения других параметров печати в приложениях Windows. Он используется в качестве простого решения для выбора принтера и параметров печати вместо самостоятельной настройки диалогового окна. Вы можете разрешить пользователям печатать много частей документов: Печать всего, Печать выделенного диапазона страниц или Печать выделенного фрагмента. Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям. Компонент <xref:System.Windows.Forms.PrintDialog> наследуется от класса <xref:System.Windows.Forms.CommonDialog>.

## <a name="working-with-the-component"></a>Работа с компонентом

Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для вывода диалогового окна во время выполнения. Этот компонент имеет свойства, относящиеся к одному заданию печати (<xref:System.Drawing.Printing.PrintDocument> класс) или параметрам отдельного принтера (класс<xref:System.Drawing.Printing.PrinterSettings>). Любой из них, в свою очередь, может совместно использоваться несколькими принтерами.

При добавлении в форму <xref:System.Windows.Forms.PrintDialog> компонент отображается в области в нижней части конструктор Windows Forms в Visual Studio.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.PrintDialog>
- [Компонент PrintDialog](printdialog-component-windows-forms.md)
