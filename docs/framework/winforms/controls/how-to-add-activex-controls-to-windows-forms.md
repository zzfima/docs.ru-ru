---
title: "Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms."
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9328400917208dde9f81b493fbf26c6080dc9c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms.
Хотя конструктор Windows Forms оптимизирован для размещения элементов управления Windows Forms, можно также поместить элементы управления ActiveX в формах Windows Forms.  
  
> [!CAUTION]
>  Существуют ограничения производительности для форм Windows Forms, когда к ним добавляются элементы управления ActiveX.  
  
 Прежде чем добавлять элементы управления ActiveX в форму, необходимо добавить их в область элементов. Дополнительные сведения см. в разделе [COM-компонентов, Настройка области элементов диалоговое окно](http://msdn.microsoft.com/en-us/171333f3-f207-4e02-bbdc-17862556212c).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a>Добавление элемента управления ActiveX в форме Windows Forms  
  
-   Дважды щелкните элемент управления на панели инструментов.  
  
     [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]Добавляет все ссылки на элемент управления в проекте. Дополнительные сведения о том, что следует учитывать при использовании элементов управления ActiveX в формах Windows Forms см. в разделе [вопросы размещения элемента управления ActiveX в формы Windows Forms](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).  
  
    > [!NOTE]
    >  Импорта элемента управления ActiveX Windows Forms (AxImp.exe) создает аргументы события другого типа, чем требуется при импортировании библиотек динамической компоновки ActiveX. Аргументы, создаваемые с AxImp.exe примерно следующего содержания: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, когда `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` ожидается. Имейте в виду, что подобное нарушение правил не мешает кода правильной работе. Дополнительные сведения см. в разделе [импорта элемента управления ActiveX Windows Forms (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).  
  
## <a name="see-also"></a>См. также  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Сравнение элементов управления и программируемых объектов в разных языках и библиотеках](http://msdn.microsoft.com/en-us/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Упорядочение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Функциональная классификация элементов управления Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
