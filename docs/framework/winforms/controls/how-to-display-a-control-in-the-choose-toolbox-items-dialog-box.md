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
ms.openlocfilehash: fdda72d60b0f18e76b03e9b7f05060a09763a3f7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43527627"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов
При разработке и распределить элементы управления, вы можете эти элементы управления отображались в **Выбор элементов панели элементов** диалоговое окно, которое отображается при щелчке правой кнопкой мыши **элементов** и выберите  **Выбор элементов**. Вы можете включить элемент управления появился в этом диалоговом окне, используя процедуру регистрации AssemblyFoldersEx.  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a>Отображение элемента управления в диалоговом окне Выбор элементов панели элементов  
  
-   Установите сборку элемента управления в глобальном кэше сборок. Дополнительные сведения см. в разделе [как: Установка сборки в глобальный кэш сборок](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
  
     - или -  
  
-   Зарегистрируйте элемент управления и его связанные сборки времени разработки, используя процедуру регистрации AssemblyFoldersEx. AssemblyFoldersEx находится в расположении реестра, где сторонние поставщики сохраняют пути для каждой версии платформы, на которой они поддерживают. Разрешение во время разработки можно искать в этом расположении реестра поиск эталонных сборок. Скрипт реестра можно указать элементы управления, которые должны отображаться на панели элементов. Дополнительные сведения см. в разделе [развертывание пользовательского элемента управления и сборки времени разработки (Visual Studio 2013)](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).  
  
## <a name="see-also"></a>См. также  
 [Диалоговое окно "Выбор элементов панели элементов" (Visual Studio)](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [Развертывание пользовательского элемента управления и сборки времени разработки (Visual Studio 2013)](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)  
 [Создание элементов управления Windows Forms во время разработки](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [Практическое руководство. Установка сборки в глобальный кэш сборок](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
