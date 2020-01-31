---
title: Общие сведения о компоненте PageSetupDialog
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: a891cb8cc77007d7591d41461c94f61c077eb300
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744340"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>Общие сведения о компоненте PageSetupDialog (Windows Forms)

Компонент Windows Forms <xref:System.Windows.Forms.PageSetupDialog> является предварительно настроенным диалоговым окном, используемым для задания сведений о странице для печати в приложениях Windows. Используйте его в приложении Windows в качестве простого решения для пользователей, чтобы задать параметры страницы вместо настройки собственного диалогового окна. Можно разрешить пользователям задавать настройки границ и полей, верхние и нижние колонтитулы, а также книжную или альбомную ориентацию. Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.

## <a name="key-properties-and-methods"></a>Ключевые свойства и методы

Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для вывода диалогового окна во время выполнения. Этот компонент имеет свойства, которые могут быть связаны с одной страницей (<xref:System.Drawing.Printing.PrintDocument> класс) или с любым документом (<xref:System.Drawing.Printing.PageSettings> класса). Кроме того, компонент <xref:System.Windows.Forms.PageSetupDialog> можно использовать для определения конкретных параметров принтера, которые хранятся в классе <xref:System.Drawing.Printing.PrinterSettings>.

При добавлении в форму <xref:System.Windows.Forms.PageSetupDialog> компонент отображается в области в нижней части конструктор Windows Forms в Visual Studio.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.PageSetupDialog>
- [PageSetupDialog Component](pagesetupdialog-component-windows-forms.md)
