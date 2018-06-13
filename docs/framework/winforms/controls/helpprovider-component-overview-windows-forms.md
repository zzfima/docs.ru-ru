---
title: Общие сведения о компоненте HelpProvider (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
ms.openlocfilehash: 5ad74b862c09734f3490210cb6898945a3c787fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528623"
---
# <a name="helpprovider-component-overview-windows-forms"></a>Общие сведения о компоненте HelpProvider (Windows Forms)
Windows Forms [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) компонент используется для связывания HTML файл справки версии 1.x (CHM-файл, созданный с помощью средства HTML Help Workshop, или HTM-файл) с приложением Windows. Можно предоставить справку в различными способами:  
  
-   Предоставить контекстную справку для элементов управления в формах Windows Forms.  
  
-   Предоставить контекстную справку для определенного диалогового или конкретных элементов управления в диалоговом окне.  
  
-   Откройте файл справки для конкретной области, например для главной страницы содержимое из таблицы, индекса или для функции поиска.  
  
## <a name="using-the-help-provider"></a>С помощью поставщика справки  
 Добавление <xref:System.Windows.Forms.HelpProvider> компонент в форме Windows Forms позволяет других элементов управления на форме, предоставляют свойства справки <xref:System.Windows.Forms.HelpProvider> компонента. Это дает возможность предоставить справку для элементов управления на форме Windows Forms. Можно связать файл справки с <xref:System.Windows.Forms.HelpProvider> компонента с помощью <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> свойство. Укажите тип путем вызова справки <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> и указания значения из <xref:System.Windows.Forms.HelpNavigator> перечисления для указанного элемента управления. Укажите ключевое слово или раздел для справки, вызвав <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> метод.  
  
 При необходимости, чтобы связать определенную строку Help с другим элементом управления, используйте <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> метод. Строка, которая связана с элементом управления с помощью этого метода отображается во всплывающем окне при нажатии клавиши F1, когда элемент управления имеет фокус.  
  
 Если <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> не был задан, необходимо использовать <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> предоставить текст справки. Если одновременно заданы <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> и строка справки на основе справки <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> будет иметь приоритет.  
  
> [!NOTE]
>  Возникли проблемы с использованием относительного пути при при указании пути к файлу справки в <xref:System.Windows.Forms.Help.ShowHelp%2A> метода или <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> свойства <xref:System.Windows.Forms.HelpProvider> элемента управления. Таким образом необходимо с помощью абсолютный путь к файлу справки.  
  
## <a name="see-also"></a>См. также  
 [Справочные системы в приложениях Windows Forms](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)
