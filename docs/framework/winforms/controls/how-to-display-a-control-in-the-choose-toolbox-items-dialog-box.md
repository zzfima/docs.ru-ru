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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9a6938b4fe651e13f3ec96642db6027143f1f028
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015893"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов

При разработке и распространении элементов управления может потребоваться, чтобы они отображались в диалоговом окне **Выбор элементов панели элементов** Visual Studio, которое отображается, если щелкнуть правой кнопкой мыши **панель элементов** и выбрать пункт **выбрать элементы**. Можно включить отображение элемента управления в этом диалоговом окне с помощью процедуры регистрации AssemblyFoldersEx.

Для вывода элемента управления в диалоговом окне Выбор элементов панели элементов выполните следующие действия.

- Установите сборку элемента управления в глобальный кэш сборок. Дополнительные сведения см. в разделе [Практическое руководство. Установка сборки в глобальный кэш сборок](../../app-domains/how-to-install-an-assembly-into-the-gac.md)

  -или-

- Зарегистрируйте элемент управления и связанные с ним сборки времени разработки с помощью процедуры регистрации AssemblyFoldersEx. AssemblyFoldersEx — это расположение реестра, в котором сторонние поставщики хранят пути для каждой поддерживаемой версии платформы. Разрешение во время разработки может найти в этом расположении реестра сведения о ссылочных сборках. Скрипт реестра может указывать элементы управления, которые должны отображаться на панели элементов.

## <a name="see-also"></a>См. также

- [Создание элементов управления Windows Forms во время разработки](developing-windows-forms-controls-at-design-time.md)
- [Практическое руководство. Установка сборки в глобальный кэш сборок](../../app-domains/how-to-install-an-assembly-into-the-gac.md)
- [Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
