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
ms.openlocfilehash: cefc590bb3011b282392504a78ac5c393c58493e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965696"
---
# <a name="helpprovider-component-overview-windows-forms"></a>Общие сведения о компоненте HelpProvider (Windows Forms)
Компонент Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) используется для связывания файла справки HTML Help 1. x (либо файла. chm, созданного с помощью справки HTML или файла. htm) с приложением Windows. Получить справку можно различными способами:  
  
- Предоставьте контекстную справку для элементов управления на Windows Forms.  
  
- Предоставить контекстную справку по конкретному диалоговому окну или определенным элементам управления в диалоговом окне.  
  
- Открытие файла справки для конкретных областей, например главной страницы оглавления, индекса или функции поиска.  
  
## <a name="using-the-help-provider"></a>Использование поставщика справки  
 Добавление компонента в форму Windows позволяет другим элементам управления формы предоставлять свойства <xref:System.Windows.Forms.HelpProvider> справки компонента. <xref:System.Windows.Forms.HelpProvider> Это позволяет предоставить справку для элементов управления в форме Windows Forms. Файл справки можно связать с <xref:System.Windows.Forms.HelpProvider> компонентом <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> с помощью свойства. Вы указываете тип справки, предоставляемый вызовом <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> , и предоставляя значение <xref:System.Windows.Forms.HelpNavigator> из перечисления для указанного элемента управления. Вы предоставляете ключевое слово или раздел для справки, <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> вызывая метод.  
  
 Кроме того, чтобы связать определенную строку справки с другим элементом управления, используйте <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> метод. Строка, связываемая с элементом управления с помощью этого метода, отображается во всплывающем окне, когда пользователь нажимает клавишу F1, когда элемент управления находится в фокусе.  
  
 Если <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> параметр не задан, необходимо использовать <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> для предоставления текста справки. Если заданы <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> и, и строка справки, то Справка, основанная на <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> , будет иметь приоритет.  
  
> [!NOTE]
> При указании пути к файлу справки в <xref:System.Windows.Forms.Help.ShowHelp%2A> методе или <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> свойстве <xref:System.Windows.Forms.HelpProvider> элемента управления могут возникнуть проблемы с использованием относительного пути. Поэтому для указания файла справки следует использовать абсолютный путь к файлу.  
  
## <a name="see-also"></a>См. также

- [Справочные системы в приложениях Windows Forms](../advanced/help-systems-in-windows-forms-applications.md)
