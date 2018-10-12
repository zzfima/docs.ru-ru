---
title: Командная строка разработчика для Visual Studio
ms.date: 08/14/2018
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 20dc7caa9e4c3e023bf2848b1dd8c63a9b94a01b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170013"
---
# <a name="developer-command-prompt-for-visual-studio"></a>Командная строка разработчика для Visual Studio

Командная строка разработчика для Visual Studio облегчает использование средств .NET Framework. Также эта командная строка автоматически задает определенные переменные среды.

> [!div class="button"]
[Скачать Visual Studio 2012](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

## <a name="search-for-the-command-prompt-on-your-machine"></a>Поиск командной строки на компьютере

В зависимости от версии Visual Studio и дополнительно установленных пакетов SDK может иметься несколько вариантов командной строки. Например, в 64-разрядных версиях Visual Studio представлены 32-разрядная и 64-разрядная версии командной строки. (32-разрядная и 64-разрядная версии большинства инструментов являются одинаковыми. Однако некоторые инструменты работают по-разному в 32-разрядных и 64-разрядных средах.) Если приведенные ниже действия не работают, можно попробовать [найти файлы на компьютере вручную](#manually-locate-the-files-on-your-machine) или [запустить командную строку из Visual Studio](#run-the-command-prompt-from-inside-visual-studio).

### <a name="in-windows-10"></a>В Windows 10

1. В поле поиска на панели задач начните вводить имя средства, например `dev` или `developer command prompt`. Откроется список установленных приложений, которые соответствуют вашему шаблону поиска. Если вы ищете другую командную строку, попробуйте ввести другое условие поиска, например `prompt`.

2. Выберите элемент **Командная строка разработчика** (или нужную командную строку).

### <a name="in-windows-81"></a>Windows 8.1

1. Перейдите на **начальный** экран, например нажав клавишу с логотипом Windows ![логотип Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.

2. На **начальном экране** нажмите **CTRL**+**TAB**, чтобы открыть список **приложений**, а затем введите `V`. Появится список, включающий все установленные командные строки Visual Studio.

3. Выберите элемент **Командная строка разработчика** (или нужную командную строку).

### <a name="in-windows-8"></a>Windows 8

1. Перейдите на **начальный** экран, например нажав клавишу с логотипом Windows ![логотип Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.

2. На **начальном экране** нажмите на клавиатуре клавишу с логотипом Windows![логотип Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.

3. Выберите значок **представления "Приложения"** в нижней части экрана, а затем введите `V`. Появится список, включающий все установленные командные строки Visual Studio.

4. Выберите элемент **Командная строка разработчика** (или нужную командную строку).

### <a name="in-windows-7"></a>Windows 7

1. В меню **Пуск** разверните список **Все программы**, а затем папку **Microsoft Visual Studio**.

2. В зависимости от установленной версии Visual Studio выберите пункт **Инструменты Visual Studio**, **Командная строка Visual Studio** или нужную командную строку.

Если установлен пакет SDK, например [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) или [предыдущие версии](https://developer.microsoft.com/windows/downloads/sdk-archive), в системе могут быть дополнительные командные строки для архитектур ARM, x86 или x64. Требуемая версия командной строки указана в документации по соответствующим инструментам.

## <a name="manually-locate-the-files-on-your-machine"></a>Поиск файлов на компьютере вручную

Обычно ярлыки для установленных командных строк помещаются в папку **меню "Пуск"** для Visual Studio, например в C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools. Но если по какой-то причине поиск командной строки не дает ожидаемых результатов, попробуйте вручную найти ярлык на компьютере. Попробуйте ввести имя файла командной строки, например *VsDevCmd.bat*, или перейдите в папку средств, например в C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (точный путь зависит от версии, выпуска и расположения установки Visual Studio).

## <a name="run-the-command-prompt-from-inside-visual-studio"></a>Запуск командной строки из Visual Studio

Для упрощения доступа можно включить командную строку разработчика для Visual Studio или другую командную строку в меню **Инструменты** в Visual Studio. Чтобы сделать средство доступным, добавьте его в список внешних инструментов. Ниже приведены инструкции.

1. Запустите Visual Studio.

2. Выберите меню **Инструменты** и затем выберите в нем пункт **Внешние инструменты**.

3. В диалоговом окне **Внешние инструменты** нажмите кнопку **Добавить**. Появится новый элемент.

4. Введите **заголовок** для нового пункта меню, например `Command Prompt`.

5. В поле **Команда** укажите файл, который должен запускаться, например `%comspec%` или `C:\Windows\System32\cmd.exe`.

6. В поле **Аргументы** укажите, где найти конкретную командную строку, которую вы хотите использовать, например `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (эта команда запускает командную строку разработчика, установленную с Visual Studio 2017 Enterprise). Измените это значение в соответствии с вашей версией, выпуском и расположением установки Visual Studio.

7. Выберите значение для поля **Исходный каталог**, например **Каталог проекта**.

8. Нажмите кнопку **ОК** .

   Новый элемент добавляется в меню, и вы можете вызывать командную строку из меню **Инструменты**.

   ![Пункт меню "Командная строка" в Visual Studio](media/command-prompt-vs-menu.png)

## <a name="see-also"></a>См. также

- [Инструменты](../../../docs/framework/tools/index.md)
- [Управление внешними инструментами](/visualstudio/ide/managing-external-tools)
