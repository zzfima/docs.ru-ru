---
title: Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов
ms.date: 08/23/2019
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: db4b3ac020e967a6a0c291103d825ac71cebda23
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458279"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов

При разработке и распространении элементов управления может потребоваться, чтобы они отображались в диалоговом окне **Выбор элементов панели элементов** Visual Studio, которое отображается, если щелкнуть правой кнопкой мыши **панель элементов** и выбрать пункт **выбрать элементы**. Можно включить отображение элемента управления в этом диалоговом окне с помощью процедуры регистрации AssemblyFoldersEx.

Для вывода элемента управления в диалоговом окне Выбор элементов панели элементов выполните следующие действия.

- Установите сборку элемента управления в глобальный кэш сборок. Дополнительные сведения см. в разделе [Практическое руководство. Установка сборки в глобальный кэш сборок](../../app-domains/install-assembly-into-gac.md).

  \- или -

- Зарегистрируйте элемент управления и связанные с ним сборки времени разработки с помощью процедуры регистрации AssemblyFoldersEx. AssemblyFoldersEx — это расположение реестра, в котором сторонние поставщики хранят пути для каждой поддерживаемой версии платформы. Разрешение во время разработки может найти в этом расположении реестра сведения о ссылочных сборках. Скрипт реестра может указывать элементы управления, которые должны отображаться на панели элементов.

## <a name="see-also"></a>См. также

- [Создание элементов управления Windows Forms во время разработки](developing-windows-forms-controls-at-design-time.md)
- [Практическое руководство. Установка сборки в глобальный кэш сборок](../../app-domains/install-assembly-into-gac.md)
- [Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
