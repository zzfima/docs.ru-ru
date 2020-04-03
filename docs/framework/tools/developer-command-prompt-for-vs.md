---
title: Командная строка разработчика для Visual Studio
ms.date: 01/05/2020
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
ms.openlocfilehash: f028281d477284acf3ac4dac63f5ddbbd79f5259
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "75715828"
---
# <a name="developer-command-prompt-for-visual-studio"></a>Командная строка разработчика для Visual Studio

**Командная строка разработчика** для Visual Studio облегчает использование средств .NET Framework. Это командная строка, которая автоматически устанавливает определенные переменные среды. После открытия **Командной строки разработчика**, вы можете ввести команды для [средств платформы .NET Framework](index.md), например `ildasm` или `clrver`.

## <a name="prerequisites"></a>Предварительные требования

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a>Поиск командной строки на компьютере

В зависимости от версии Visual Studio, дополнительно установленных пакетов SDK и рабочих нагрузок может иметься несколько вариантов командных строк. Если приведенные ниже действия не работают, можно попробовать [найти файлы на компьютере вручную](#manually-locate-the-files-on-your-machine) или [запустить командную строку из Visual Studio](#start-the-command-prompt-from-inside-visual-studio).

### <a name="windows-10"></a>Windows 10

1. Выберите **Пуск** ![клавишу с логотипом Windows на клавиатуре.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png) и прокрутите до буквы **V**.

1. Разверните папку **Visual Studio 2019**.

1. Выберите элемент **Командная строка разработчика для VS 2019** (или нужную командную строку).

   Или вы можете начать вводить имя командной строки в поле поиска на панели задач и выбрать нужный результат, поскольку список результатов начнет отображать найденные совпадения.

   ![GIF с анимацией, показывающий поведение поиска в Windows 10](./media/developer-command-prompt-for-vs/windows10-search.gif)

### <a name="windows-81"></a>Windows 8.1

1. Перейдите на экран **Пуск**, нажав клавишу с логотипом Windows ![Клавиша с логотипом Windows на клавиатуре.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png) на клавиатуре, например.

1. На **начальном экране** нажмите **Ctrl**+**Tab**, чтобы открыть список **приложений**, а затем нажмите **V**. Появится список, включающий все установленные командные строки Visual Studio.

1. Выберите элемент **Командная строка разработчика для VS 2019** (или нужную командную строку).

### <a name="windows-7"></a>Windows 7

1. Выберите **Пуск** а затем разверните **Все программы**.

1. Выберите **Visual Studio 2019** > **Инструменты Visual Studio** > **Командная строка разработчика для VS 2019**, или нужную командную строку.

   ![Меню "Пуск" в Windows 7 с выделенной командной строкой](./media/developer-command-prompt-for-vs/windows7-menu.png)

Если установлены другие пакеты SDK, например, [пакет SDK для Windows 10](https://developer.microsoft.com/windows/downloads/windows-10-sdk) или [предыдущих версий](https://developer.microsoft.com/windows/downloads/sdk-archive), могут появиться дополнительные командные строки. Требуемая версия командной строки указана в документации по соответствующим инструментам.

## <a name="manually-locate-the-files-on-your-machine"></a>Поиск файлов на компьютере вручную

Обычно ярлыки для установленных командных строк помещаются в папку меню **Пуск** для Visual Studio, например в *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools*. Но если по какой-то причине поиск командной строки не дает ожидаемых результатов, попробуйте вручную найти ярлык на компьютере. Попробуйте найти имя файла командной строки, например, *VsDevCmd.bat*или перейдите в папку **Инструменты**, например, *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Community\Common7\Tools* (путь изменяется в соответствии с версией Visual Studio, выпуском и расположением установки).

## <a name="start-the-command-prompt-from-inside-visual-studio"></a>Запуск командной строки из Visual Studio

Для более удобного доступа **Командную строку разработчика** или любую другую командную строку можно добавить в меню **Инструменты** в Visual Studio. Чтобы сделать средство доступным, добавьте его в список внешних инструментов. Ниже приведены инструкции.

1. Запустите Visual Studio.

1. В начальном окне выберите **Продолжить без кода**.

1. В строке меню, выберите **Инструменты** > **Внешние Инструменты**.

1. В диалоговом окне **Внешние инструменты** нажмите кнопку **Добавить**. Появится новый элемент.

1. Введите **Заголовок** для нового пункта меню, например `Command Prompt`.

1. В поле **Команда** укажите файл, который должен запускаться, например `%comspec%` или `C:\Windows\System32\cmd.exe`.

1. В поле **Аргументы** укажите, где найти конкретную командную строку, которую вы хотите использовать, например `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`. Эта команда запускает **Командную строку разработчика**, установленную вместе с Visual Studio 2019 Community. Измените это значение в соответствии с вашей версией, выпуском и расположением установки Visual Studio.

1. В поле **Исходный каталог** укажите каталог, в котором будет запускаться командная строка. Выберите значение, например **Каталог проекта**, нажав стрелку рядом с полем.

1. Нажмите кнопку **ОК** .

   ![Диалоговое окно "Внешние инструменты" с заполненными значениями полей.](./media/developer-command-prompt-for-vs/add-external-tool.png)

   В меню добавляется новый пункт и командную строку можно вызвать из меню **Инструменты**.

   ![Пункт меню "Командная строка" в Visual Studio](./media/developer-command-prompt-for-vs/command-prompt-vs-menu.png)

## <a name="see-also"></a>См. также

- [Инструменты .NET Framework](index.md)
- [Управление внешними инструментами](/visualstudio/ide/managing-external-tools)
- [Использование набора инструментов C++ Microsoft из командной строки](/cpp/build/building-on-the-command-line)
