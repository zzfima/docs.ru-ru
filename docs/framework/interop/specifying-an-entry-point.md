---
title: Задание точки входа
ms.date: 03/30/2017
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6065e06fa4fb51cd0cd746a1619f8a611f2fc30b
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65064099"
---
# <a name="specifying-an-entry-point"></a>Задание точки входа
Точка входа определяет расположение функции в библиотеке DLL. В управляемом проекте исходное имя или порядковый номер точки входа целевой функции определяет эту функцию в границах взаимодействия. Вы можете сопоставить точку входа с другим именем, чтобы фактически переименовать функцию.  
  
 Ниже перечислено, зачем может потребоваться переименовывать функции DLL:  
  
- чтобы избежать использования имен функций API, в которых учитывается регистр символов;  
  
- чтобы привести имена в соответствие с существующими стандартами именования;  
  
- чтобы сделать возможным вызов функций, принимающих данные разных типов (путем объявления нескольких версий одной и той же функции DLL);  
  
- чтобы упростить применение интерфейсов API, которые содержат версии функции для ANSI и Юникода.  
  
 В этом разделе показано, как переименовать функцию DLL в управляемом коде.  
  
## <a name="renaming-a-function-in-visual-basic"></a>Переименование функции в Visual Basic  
 В Visual Basic для установки поля <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> используется ключевое слово **Function** в операторе **Declare**. В приведенном ниже примере показан базовый вариант объявления.  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
 Как показано в следующем примере, можно заменить точку входа **MessageBox** на **MsgBox**, включив в определение ключевое слово **Alias**. В обоих примерах ключевое слово **Auto** позволяет не указывать версию кодировки для точки входа. Дополнительные сведения о выборе кодировки см. в разделе [Определение кодировки](../../../docs/framework/interop/specifying-a-character-set.md).  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MsgBox _
        Lib "user32.dll" Alias "MessageBox" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="renaming-a-function-in-c-and-c"></a>Переименование функции в C# и C++  
 Для задания функции DLL по имени или порядковому номеру можно использовать поле <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>. Если имя функции в определении метода совпадает с именем точки входа в библиотеке DLL, явно задавать функцию с помощью поля **EntryPoint** не требуется. В противном случае, чтобы указать имя или порядковый номер, следует использовать одну из следующих форм атрибута:  
  
```csharp
[DllImport("DllName", EntryPoint = "Functionname")]
[DllImport("DllName", EntryPoint = "#123")]
```
  
 Обратите внимание, что порядковому номеру должен предшествовать знак #.  
  
 В приведенном ниже примере показан способ замены в коде **MessageBoxA** на **MsgBox** с помощью поля **EntryPoint**.  
  
```csharp
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll", EntryPoint = "MessageBoxA")]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```
  
```cpp
using namespace System;
using namespace System::Runtime::InteropServices;

typedef void* HWND;
[DllImport("user32", EntryPoint = "MessageBoxA")]
extern "C" int MsgBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Создание прототипов в управляемом коде](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [Примеры вызовов неуправляемого кода](../../../docs/framework/interop/platform-invoke-examples.md)
- [Маршалинг данных при вызове неуправляемого кода](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
