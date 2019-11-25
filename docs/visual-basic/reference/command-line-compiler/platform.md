---
title: -platform
ms.date: 03/13/2018
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
ms.openlocfilehash: a6226b73d5d5d4d48a71afe39e8a546019d4c0bc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352348"
---
# <a name="-platform-visual-basic"></a>-platform (Visual Basic)
Указывает, на какой версии платформы среды CLR может запускаться выходной файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`x86`|Компилирует сбору для запуска в 32-разрядной среде CLR с архитектурой x86.|  
|`x64`|Компилирует сбору для запуска в 64-разрядной среде CLR на компьютере, поддерживающем набор инструкций AMD64 или EM64T.|  
|`Itanium`|Компилирует сбору для запуска в 64-разрядной среде CLR на компьютере с процессором Itanium.|  
|`arm`|Компилирует сбору для запуска на компьютере с процессором ARM.|  
|`anycpu`|Компилирует сбору для запуска на любой платформе. Приложение будет выполняться как 32-разрядное приложение в 32-разрядных версиях Windows и как 64-разрядное приложение в 64-разрядных версиях Windows. Этот флаг — значение по умолчанию.|  
|`anycpu32bitpreferred`|Компилирует сбору для запуска на любой платформе. Приложение будет выполняться как 32-разрядное приложение в 32-разрядных и 64-разрядных версиях Windows. This flag is valid only for executables (.EXE) and requires .NET Framework 4.5.|  
  
## <a name="remarks"></a>Заметки  
 Используйте параметр `-platform`, чтобы указать процессор назначения для выходного файла.  
  
 В целом, сборки .NET Framework, написанные на Visual Basic, будут работать одинаково вне зависимости от платформы. Тем не менее, в некоторых случаях поведение программ на разных платформах может различаться. Вот эти случаи:  
  
- Структуры, содержащие члены, размер которых изменяется в зависимости от платформы, например, любые типы указателей.  
  
- Арифметика указателя, содержащая постоянные размеры.  
  
- Неверный вызов платформ или объявления СОМ, использующие дескрипторы `Integer` вместо <xref:System.IntPtr>.  
  
- Приведение <xref:System.IntPtr> к `Integer`.  
  
- Использование вызов платформ или взаимодействия СОМ с компонентами, существующими не на всех платформах.  
  
 The **-platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on. В частности:  
  
- Если целевой является 64-разрядная платформа, а приложение запущено на 32-разрядном компьютере, сообщение об ошибке появится гораздо раньше и будет более точным, чем сообщение об ошибке, которое появится без этого параметра.  
  
- Если задать флаг `x86` для параметра, а потом запустить приложение на 64-разрядном компьютере, приложение будет запущено в подсистеме WOW, а не непосредственно.  
  
 В 64-разрядной ОС Windows:  
  
- Сборки, скомпилированные с параметром `-platform:x86`, будут выполняться в 32-разрядной среде CLR с WOW64.  
  
- Исполняемые файлы, скомпилированные с параметром `-platform:anycpu`, будут выполняться в 64-разрядной среде CLR.  
  
- Библиотеки DLL, скомпилированные с параметром `-platform:anycpu`, будут выполняться в тоже де среде CLR, что и процесс, загрузивший эти библиотеки.  
  
- Исполняемые файлы, скомпилированные с параметром `-platform:anycpu32bitpreferred`, будут выполняться в 32-разрядной среде CLR.  
  
 For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](../../../framework/64-bit-apps.md).  
  
### <a name="to-set--platform-in-the-visual-studio-ide"></a>To set -platform in the Visual Studio IDE  
  
1. In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.  
  
2. On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.  
  
     For more information, see [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование параметра компилятора `-platform`.  
  
```console
vbc -platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a>См. также

- [-target (Visual Basic)](target.md)
- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
