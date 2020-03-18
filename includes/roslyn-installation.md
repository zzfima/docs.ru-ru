---
ms.openlocfilehash: 2872c5909b382e01fdd231019a12970caa3b77d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "72526772"
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
