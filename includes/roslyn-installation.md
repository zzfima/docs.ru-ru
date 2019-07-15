---
ms.openlocfilehash: dab6b435a885d862d08f94dd31de79625f19bcc0
ms.sourcegitcommit: 6472349821dbe202d01182bc2cfe9d7176eaaa6c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2019
ms.locfileid: "67870511"
---
## <a name="installation-instructions---visual-studio-installer"></a>Инструкции по установке — Visual Studio Installer

Найти **SDK-пакет .NET Compiler Platform** в **Visual Studio Installer** можно двумя способами:

### <a name="install-using-the-visual-studio-installer---workloads-view"></a>Установка с помощью Visual Studio Installer — представление "Рабочие нагрузки"

SDK-пакет .NET Compiler Platform не выбирается автоматически в рамках рабочей нагрузки разработки расширений Visual Studio. Его необходимо выбрать как дополнительный компонент.

1. Запустите **Visual Studio Installer**. 
1. Выберите **Изменить**. 
1. Отметьте рабочую нагрузку **Разработка расширений Visual Studio**.
1. Откройте узел **Разработка расширений Visual Studio** в дереве сводки.
1. Установите флажок **SDK-пакет .NET Compiler Platform**. Нужный пакет будет представлен последним в списке дополнительных компонентов.

Кроме того, вы можете настроить **редактор DGML** для отображения диаграмм в средстве визуализации:

1. Откройте узел **Отдельные компоненты** в дереве сводки.
1. Установите флажок **Редактор DGML**

### <a name="install-using-the-visual-studio-installer---individual-components-tab"></a>Установка с помощью Visual Studio Installer — вкладка "Отдельные компоненты"

1. Запустите **Visual Studio Installer**. 
1. Выберите **Изменить**. 
1. Откройте вкладку **Отдельные компоненты**. 
1. Установите флажок **SDK-пакет .NET Compiler Platform**. Нужный пакет будет представлен в разделе **Компиляторы, средства сборки и среды выполнения** в самом начале.

Кроме того, вы можете настроить **редактор DGML** для отображения диаграмм в средстве визуализации:

1. Установите флажок **Редактор DGML**. Нужный пакет будет представлен в разделе **Средства для работы с кодом**.
