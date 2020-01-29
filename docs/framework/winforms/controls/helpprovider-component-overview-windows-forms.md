---
title: Общие сведения о компоненте HelpProvider
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
ms.openlocfilehash: 74d35dfa39a605cb1e1e85cc3aeda834e1c60669
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738727"
---
# <a name="helpprovider-component-overview-windows-forms"></a>Общие сведения о компоненте HelpProvider (Windows Forms)
Компонент Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) используется для связывания файла справки HTML Help 1. x (либо файла. chm, созданного с помощью справки HTML или файла. htm) с приложением Windows. Получить справку можно различными способами:  
  
- Предоставьте контекстную справку для элементов управления на Windows Forms.  
  
- Предоставить контекстную справку по конкретному диалоговому окну или определенным элементам управления в диалоговом окне.  
  
- Открытие файла справки для конкретных областей, например главной страницы оглавления, индекса или функции поиска.  
  
## <a name="using-the-help-provider"></a>Использование поставщика справки  
 Добавление <xref:System.Windows.Forms.HelpProvider> компонента в форму Windows Forms позволяет другим элементам управления в форме предоставлять свойства справки компонента <xref:System.Windows.Forms.HelpProvider>. Это позволяет предоставить справку для элементов управления в форме Windows Forms. Файл справки можно связать с компонентом <xref:System.Windows.Forms.HelpProvider> с помощью свойства <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>. Вы указываете тип справки, предоставленный при вызове <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A>, и предоставляя значение из перечисления <xref:System.Windows.Forms.HelpNavigator> для указанного элемента управления. Вы предоставляете ключевое слово или раздел для справки, вызывая метод <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>.  
  
 Кроме того, чтобы связать определенную строку справки с другим элементом управления, используйте метод <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>. Строка, связываемая с элементом управления с помощью этого метода, отображается во всплывающем окне, когда пользователь нажимает клавишу F1, когда элемент управления находится в фокусе.  
  
 Если <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> не задано, для предоставления текста справки необходимо использовать <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>. Если заданы как <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>, так и строка справки, то Справка на основе <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> будет иметь приоритет.  
  
> [!NOTE]
> При указании пути к файлу справки в методе <xref:System.Windows.Forms.Help.ShowHelp%2A> или <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> свойства элемента управления <xref:System.Windows.Forms.HelpProvider> могут возникнуть проблемы с использованием относительного пути. Поэтому для указания файла справки следует использовать абсолютный путь к файлу.  
  
## <a name="see-also"></a>См. также:

- [Справочные системы в приложениях Windows Forms](../advanced/help-systems-in-windows-forms-applications.md)
