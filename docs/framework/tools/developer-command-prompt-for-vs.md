---
title: "Командная строка разработчика для Visual Studio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
caps.latest.revision: "45"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e93a1d116ac0480c80e259ddbadbc65fd9539389
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="developer-command-prompt-for-visual-studio"></a>Командная строка разработчика для Visual Studio
Командная строка разработчика для Visual Studio автоматически задает переменные среды, с помощью которых можно легко использовать средства .NET Framework. Командная строка разработчика устанавливается с полными выпусками и выпусками Community Edition Visual Studio. Она не устанавливается с версиями Visual Studio Express.  
  
<a name="find"></a>   
## <a name="searching-for-the-command-prompt-on-your-machine"></a>Поиск командной строки на компьютере  
 В зависимости от версии Visual Studio и дополнительно установленных пакетов SDK может иметься несколько вариантов командной строки. Например, в 64-разрядных версиях Visual Studio представлены 32-разрядная и 64-разрядная версии командной строки. (32-разрядная и 64-разрядная версии большинства инструментов являются одинаковыми. Однако некоторые инструменты работают по-разному в 32-разрядных и 64-разрядных средах.) Если приведенные ниже действия не работают, можно выполнить [Поиск файлов на компьютере вручную](#alternative) или [Запуск командной строки из Visual Studio](#visualstudio).  
  
 **В Windows 10**  
  
1.  Откройте меню **Пуск**, например, нажав клавишу с логотипом Windows ![логотип Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.  
  
2.  В меню **Пуск** введите `dev`. Откроется список установленных приложений, которые соответствуют вашему шаблону поиска. Если вы ищете другую командную строку, попробуйте ввести другое условие поиска, например `prompt`.  
  
3.  Выберите элемент **Командная строка разработчика** (или нужную командную строку).  
  
 **В Windows 8.1**  
  
1.  Перейдите на **начальный** экран, например нажав клавишу с логотипом Windows ![логотип Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.  
  
2.  На **начальном экране** нажмите `CTRL + TAB`, чтобы открыть список **приложений**, а затем введите `V`. Появится список, включающий все установленные командные строки Visual Studio.  
  
3.  Выберите элемент **Командная строка разработчика** (или нужную командную строку).  
  
 **В Windows 8**  
  
1.  Перейдите на **начальный** экран, например нажав клавишу с логотипом Windows ![логотип Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.  
  
2.  На **начальном экране** нажмите на клавиатуре клавишу с логотипом Windows![логотип Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.  
  
3.  Выберите значок **представления "Приложения"** в нижней части экрана, а затем введите `V`. Появится список, включающий все установленные командные строки Visual Studio.  
  
4.  Выберите элемент **Командная строка разработчика** (или нужную командную строку).  
  
 **В Windows 7**  
  
1.  В меню **Пуск** разверните список **Все программы**, а затем папку **Microsoft Visual Studio**.  
  
2.  В зависимости от установленной версии Visual Studio, выберите пункт **Инструменты Visual Studio**, **Командная строка Visual Studio** или нужную командную строку.  
  
 Если установлен [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) или [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk), в системе могут быть дополнительные командные строки для архитектур ARM, x86 или x64. Требуемая версия командной строки указана в документации по соответствующим инструментам.  
  
<a name="alternative"></a>   
## <a name="manually-locating-the-files-on-your-machine"></a>Поиск файлов на компьютере вручную  
  Обычно ярлыки для установленных командных строк помещаются в папку **меню "Пуск"** для Visual Studio, например в C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2015\Visual Studio Tools.    Но если по какой-то причине поиск командной строки не дает ожидаемых результатов, попробуйте вручную найти ярлык на компьютере, чтобы использовать его.   Попробуйте ввести имя файла командной строки, например VsDevCmd.bat, или перейдите в папку средств, например в C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools (точный путь зависит от версии Visual Studio и расположения установки).  
  
<a name="visualstudio"></a>   
## <a name="running-command-prompt-from-inside-visual-studio"></a>Запуск командной строки из Visual Studio  
 Для упрощения доступа можно включить командную строку разработчика для Visual Studio или другую командную строку в меню "Инструменты" в Visual Studio, добавив ее в список внешних инструментов. Вот как это можно сделать.  
  
1.  Запустите Visual Studio.  
  
2.  Выберите меню **Инструменты** и выберите в нем пункт **Внешние инструменты...**  
  
3.  В диалоговом окне **Внешние инструменты** нажмите кнопку **Добавить**. Появится новый элемент.  
  
4.  Введите **заголовок** для нового пункта меню, например `Command Prompt`.  
  
5.  В поле **Команда** укажите файл, который должен запускаться, например `%comspec%` или `C:\Windows\System32\cmd.exe`.  
  
6.  В поле **Аргументы** укажите, где найти конкретную командную строку, которую вы хотите использовать, например `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` (это будет запускать командную строку разработчика, установленную с [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]). Это значение следует изменить в соответствии с вашей версией Visual Studio и расположением установки.  
  
7.  Выберите значение для поля **Исходный каталог**, например **Каталог проекта**.  
  
8.  Нажмите кнопку **ОК** .  
  
 После этого новый элемент добавляется в меню, и вы можете вызывать командную строку из меню **Инструменты**.  
  
## <a name="see-also"></a>См. также  
 [Инструменты](../../../docs/framework/tools/index.md)  
 [Управление внешними инструментами](/visualstudio/ide/managing-external-tools)
