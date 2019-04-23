---
title: Определение кодировки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 798fcacab5bd74dbd6569a68a3b598c0bb63a0a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087746"
---
# <a name="specifying-a-character-set"></a>Определение кодировки
Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> управляет маршалингом строк и определяет, каким образом при вызове неуправляемого кода будут обнаруживаться имена функций в библиотеке DLL. В этом разделе описываются оба механизма.  
  
 Некоторые API экспортируют две версии функций, которые принимают строковые аргументы: обычные (ANSI) и двухбайтовые (Юникод). Например, API Windows включает следующие имена точек входа для функции **MessageBox**:  
  
-   **MessageBoxA**  
  
     Обеспечивает форматирование однобайтовых символов ANSI и имеет суффикс "A" в имени точки входа. При вызове **MessageBoxA** строки всегда маршалируются в формате ANSI.  
  
-   **MessageBoxW**  
  
     Обеспечивает форматирование двухбайтовых символов Юникода и имеет суффикс "W" в имени точки входа. При вызове **MessageBoxW** строки всегда маршалируются в формате Юникод.  
  
## <a name="string-marshaling-and-name-matching"></a>Маршалинг строк и сопоставление имен  
 Поле `CharSet` принимает следующие значения:  
  
 <xref:System.Runtime.InteropServices.CharSet.Ansi> (значение по умолчанию)  
  
-   Маршалинг строк  
  
     При вызове неуправляемого кода выполняется маршалинг строк из соответствующего управляемого формата (Юникод) в формат ANSI.  
  
-   Сопоставление имен  
  
     Если поле <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> имеет значение `true` (по умолчанию для [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]), при вызове неуправляемого кода осуществляется поиск только указанного имени. Например, если указать **MessageBox**, при вызове неуправляемого кода будет выполнен поиск **MessageBox**, который может завершиться сбоем из-за невозможности найти точное совпадение.  
  
     Если поле `ExactSpelling` имеет значение `false` (по умолчанию для C++ и C#), при вызове неуправляемого кода выполняется поиск сначала неуправляемого псевдонима (**MessageBox**), а затем, если неуправляемый псевдоним не найден, управляемого имени (**MessageBoxA**). Обратите внимание, что принципы сопоставления имен ANSI и Юникода различаются.  
  
 <xref:System.Runtime.InteropServices.CharSet.Unicode>  
  
-   Маршалинг строк  
  
     При вызове неуправляемого кода строки копируются из соответствующего управляемого формата (Юникод) в формат Юникода.  
  
-   Сопоставление имен  
  
     Если поле `ExactSpelling` имеет значение `true` (по умолчанию для [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]), при вызове неуправляемого кода осуществляется поиск только указанного имени. Например, если указать **MessageBox**, при вызове неуправляемого кода будет выполнен поиск **MessageBox**, который может завершиться сбоем из-за невозможности найти точное совпадение.  
  
     Если поле `ExactSpelling` имеет значение `false` (по умолчанию для C++ и C#), при вызове неуправляемого кода выполняется поиск сначала управляемого имени (**MessageBoxW**), а затем, если управляемое имя не найдено, неуправляемого псевдонима (**MessageBox**). Обратите внимание, что принципы сопоставления имен Юникода и ANSI различаются.  
  
 <xref:System.Runtime.InteropServices.CharSet.Auto>  
  
-   При вызове неуправляемого кода во время выполнения осуществляется выбор между форматами ANSI и Юникода в соответствии с целевой платформой.  
  
## <a name="specifying-a-character-set-in-visual-basic"></a>Определение кодировки в Visual Basic  
 В следующем примере функция **MessageBox** объявляется три раза с разными кодировками. В Visual Basic можно указать поведение кодировки, добавив ключевое слово **Ansi**, **Unicode** или **Auto** в оператор объявления.  
  
 Если опустить ключевое слово кодировки, как показано в первом операторе объявления, в поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> по умолчанию будет задана кодировка ANSI. Во втором и третьем операторе в этом примере кодировка задается явно с использованием ключевого слова.  
  
```vb
Imports System

Friend Class WindowsAPI
    Friend Shared Declare Function MessageBoxA Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Shared Declare Unicode Function MessageBoxW Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Shared Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="specifying-a-character-set-in-c-and-c"></a>Определение кодировки в C# и C++  
 Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> определяет базовую кодировку как ANSI или Юникод. Кодировка определяет порядок маршалинга строковых аргументов в метод. Чтобы указать кодировку, используйте одну из следующих форм:  
  
```csharp
[DllImport("DllName", CharSet = CharSet.Ansi)]
[DllImport("DllName", CharSet = CharSet.Unicode)]
[DllImport("DllName", CharSet = CharSet.Auto)]
```
  
```cpp
[DllImport("DllName", CharSet = CharSet::Ansi)]
[DllImport("DllName", CharSet = CharSet::Unicode)]
[DllImport("DllName", CharSet = CharSet::Auto)]
```
  
 В следующем примере показаны три управляемых определения функции **MessageBox** с атрибутами, задающими кодировку. В первом определении соответствующее ключевое слово опущено, в результате чего в поле `CharSet` по умолчанию устанавливается кодировка ANSI.  
  
```csharp  
using System;
using System.Runtime.InteropServices;

internal static class WindowsAPI
{
    [DllImport("user32.dll")]
    internal static extern int MessageBoxA(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Unicode)]
    internal static extern int MessageBoxW(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Auto)]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```  
  
```cpp
typedef void* HWND;

// Can use MessageBox or MessageBoxA.
[DllImport("user32")]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Can use MessageBox or MessageBoxW.
[DllImport("user32", CharSet = CharSet::Unicode)]
extern "C" int MessageBoxW(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Must use MessageBox.
[DllImport("user32", CharSet = CharSet::Auto)]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Создание прототипов в управляемом коде](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [Примеры вызовов неуправляемого кода](../../../docs/framework/interop/platform-invoke-examples.md)
- [Маршалинг данных при вызове неуправляемого кода](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
