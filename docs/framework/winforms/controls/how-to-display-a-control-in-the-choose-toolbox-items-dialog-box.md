---
title: Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: 7e452c3d3be131b891ee26555e3085fc31b04517
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов
При разработке и распространение элементов управления, вы можете эти элементы управления отображались в **Выбор элементов панели элементов** dialog box, которое отображается при щелчке правой кнопкой мыши **элементов** и выберите  **Выберите элементы**. Можно включить элемент управления для отображения в этом диалоговом окне, используя процедуру регистрации AssemblyFoldersEx.  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a>Отображение элемента управления в диалоговом окне Выбор элементов панели элементов  
  
-   Установите сборку элемента управления в глобальный кэш сборок. Дополнительные сведения см. в разделе [как: Установка сборки в глобальный кэш сборок](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
  
     - или -  
  
-   Зарегистрируйте элемент управления и связанных с ней сборок во время разработки, используя процедуру регистрации AssemblyFoldersEx. AssemblyFoldersEx находится в расположении реестра, где сторонние поставщики хранят пути для каждой версии платформы, на которой они поддерживают. Разрешение во время разработки можно искать в этом расположении реестра указанные сборки. Скрипт реестра может задать элементы управления, которые должны отображаться на панели инструментов. Дополнительные сведения см. в разделе [развертывание пользовательского элемента управления и сборки времени разработки (Visual Studio 2013)](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).  
  
## <a name="see-also"></a>См. также  
 [Диалоговое окно "Выбор элементов панели элементов" (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [Развертывание пользовательского элемента управления и сборки времени разработки (Visual Studio 2013)](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)  
 [Создание элементов управления Windows Forms во время разработки](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [Практическое руководство. Установка сборки в глобальный кэш сборок](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
