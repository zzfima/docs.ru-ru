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
# <a name="specifying-a-character-set"></a><span data-ttu-id="c6e63-102">Определение кодировки</span><span class="sxs-lookup"><span data-stu-id="c6e63-102">Specifying a Character Set</span></span>
<span data-ttu-id="c6e63-103">Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> управляет маршалингом строк и определяет, каким образом при вызове неуправляемого кода будут обнаруживаться имена функций в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="c6e63-103">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="c6e63-104">В этом разделе описываются оба механизма.</span><span class="sxs-lookup"><span data-stu-id="c6e63-104">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="c6e63-105">Некоторые API экспортируют две версии функций, которые принимают строковые аргументы: обычные (ANSI) и двухбайтовые (Юникод).</span><span class="sxs-lookup"><span data-stu-id="c6e63-105">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="c6e63-106">Например, API Windows включает следующие имена точек входа для функции **MessageBox**:</span><span class="sxs-lookup"><span data-stu-id="c6e63-106">The Windows API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
-   **<span data-ttu-id="c6e63-107">MessageBoxA</span><span class="sxs-lookup"><span data-stu-id="c6e63-107">MessageBoxA</span></span>**  
  
     <span data-ttu-id="c6e63-108">Обеспечивает форматирование однобайтовых символов ANSI и имеет суффикс "A" в имени точки входа.</span><span class="sxs-lookup"><span data-stu-id="c6e63-108">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="c6e63-109">При вызове **MessageBoxA** строки всегда маршалируются в формате ANSI.</span><span class="sxs-lookup"><span data-stu-id="c6e63-109">Calls to **MessageBoxA** always marshal strings in ANSI format.</span></span>  
  
-   **<span data-ttu-id="c6e63-110">MessageBoxW</span><span class="sxs-lookup"><span data-stu-id="c6e63-110">MessageBoxW</span></span>**  
  
     <span data-ttu-id="c6e63-111">Обеспечивает форматирование двухбайтовых символов Юникода и имеет суффикс "W" в имени точки входа.</span><span class="sxs-lookup"><span data-stu-id="c6e63-111">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="c6e63-112">При вызове **MessageBoxW** строки всегда маршалируются в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="c6e63-112">Calls to **MessageBoxW** always marshal strings in Unicode format.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="c6e63-113">Маршалинг строк и сопоставление имен</span><span class="sxs-lookup"><span data-stu-id="c6e63-113">String Marshaling and Name Matching</span></span>  
 <span data-ttu-id="c6e63-114">Поле `CharSet` принимает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c6e63-114">The `CharSet` field accepts the following values:</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Ansi> <span data-ttu-id="c6e63-115">(значение по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c6e63-115">(default value)</span></span>  
  
-   <span data-ttu-id="c6e63-116">Маршалинг строк</span><span class="sxs-lookup"><span data-stu-id="c6e63-116">String marshaling</span></span>  
  
     <span data-ttu-id="c6e63-117">При вызове неуправляемого кода выполняется маршалинг строк из соответствующего управляемого формата (Юникод) в формат ANSI.</span><span class="sxs-lookup"><span data-stu-id="c6e63-117">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
-   <span data-ttu-id="c6e63-118">Сопоставление имен</span><span class="sxs-lookup"><span data-stu-id="c6e63-118">Name matching</span></span>  
  
     <span data-ttu-id="c6e63-119">Если поле <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> имеет значение `true` (по умолчанию для [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]), при вызове неуправляемого кода осуществляется поиск только указанного имени.</span><span class="sxs-lookup"><span data-stu-id="c6e63-119">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is `true`, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="c6e63-120">Например, если указать **MessageBox**, при вызове неуправляемого кода будет выполнен поиск **MessageBox**, который может завершиться сбоем из-за невозможности найти точное совпадение.</span><span class="sxs-lookup"><span data-stu-id="c6e63-120">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="c6e63-121">Если поле `ExactSpelling` имеет значение `false` (по умолчанию для C++ и C#), при вызове неуправляемого кода выполняется поиск сначала неуправляемого псевдонима (**MessageBox**), а затем, если неуправляемый псевдоним не найден, управляемого имени (**MessageBoxA**).</span><span class="sxs-lookup"><span data-stu-id="c6e63-121">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="c6e63-122">Обратите внимание, что принципы сопоставления имен ANSI и Юникода различаются.</span><span class="sxs-lookup"><span data-stu-id="c6e63-122">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Unicode>  
  
-   <span data-ttu-id="c6e63-123">Маршалинг строк</span><span class="sxs-lookup"><span data-stu-id="c6e63-123">String marshaling</span></span>  
  
     <span data-ttu-id="c6e63-124">При вызове неуправляемого кода строки копируются из соответствующего управляемого формата (Юникод) в формат Юникода.</span><span class="sxs-lookup"><span data-stu-id="c6e63-124">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
-   <span data-ttu-id="c6e63-125">Сопоставление имен</span><span class="sxs-lookup"><span data-stu-id="c6e63-125">Name matching</span></span>  
  
     <span data-ttu-id="c6e63-126">Если поле `ExactSpelling` имеет значение `true` (по умолчанию для [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]), при вызове неуправляемого кода осуществляется поиск только указанного имени.</span><span class="sxs-lookup"><span data-stu-id="c6e63-126">When the `ExactSpelling` field is `true`, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="c6e63-127">Например, если указать **MessageBox**, при вызове неуправляемого кода будет выполнен поиск **MessageBox**, который может завершиться сбоем из-за невозможности найти точное совпадение.</span><span class="sxs-lookup"><span data-stu-id="c6e63-127">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="c6e63-128">Если поле `ExactSpelling` имеет значение `false` (по умолчанию для C++ и C#), при вызове неуправляемого кода выполняется поиск сначала управляемого имени (**MessageBoxW**), а затем, если управляемое имя не найдено, неуправляемого псевдонима (**MessageBox**).</span><span class="sxs-lookup"><span data-stu-id="c6e63-128">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="c6e63-129">Обратите внимание, что принципы сопоставления имен Юникода и ANSI различаются.</span><span class="sxs-lookup"><span data-stu-id="c6e63-129">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Auto>  
  
-   <span data-ttu-id="c6e63-130">При вызове неуправляемого кода во время выполнения осуществляется выбор между форматами ANSI и Юникода в соответствии с целевой платформой.</span><span class="sxs-lookup"><span data-stu-id="c6e63-130">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specifying-a-character-set-in-visual-basic"></a><span data-ttu-id="c6e63-131">Определение кодировки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c6e63-131">Specifying a Character Set in Visual Basic</span></span>  
 <span data-ttu-id="c6e63-132">В следующем примере функция **MessageBox** объявляется три раза с разными кодировками.</span><span class="sxs-lookup"><span data-stu-id="c6e63-132">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="c6e63-133">В Visual Basic можно указать поведение кодировки, добавив ключевое слово **Ansi**, **Unicode** или **Auto** в оператор объявления.</span><span class="sxs-lookup"><span data-stu-id="c6e63-133">You can specify character-set behavior in Visual Basic by adding the **Ansi**, **Unicode**, or **Auto** keyword to the declaration statement.</span></span>  
  
 <span data-ttu-id="c6e63-134">Если опустить ключевое слово кодировки, как показано в первом операторе объявления, в поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> по умолчанию будет задана кодировка ANSI.</span><span class="sxs-lookup"><span data-stu-id="c6e63-134">If you omit the character-set keyword, as is done in the first declaration statement, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span> <span data-ttu-id="c6e63-135">Во втором и третьем операторе в этом примере кодировка задается явно с использованием ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="c6e63-135">The second and third statements in the example explicitly specify a character set with a keyword.</span></span>  
  
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
  
## <a name="specifying-a-character-set-in-c-and-c"></a><span data-ttu-id="c6e63-136">Определение кодировки в C# и C++</span><span class="sxs-lookup"><span data-stu-id="c6e63-136">Specifying a Character Set in C# and C++</span></span>  
 <span data-ttu-id="c6e63-137">Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> определяет базовую кодировку как ANSI или Юникод.</span><span class="sxs-lookup"><span data-stu-id="c6e63-137">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="c6e63-138">Кодировка определяет порядок маршалинга строковых аргументов в метод.</span><span class="sxs-lookup"><span data-stu-id="c6e63-138">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="c6e63-139">Чтобы указать кодировку, используйте одну из следующих форм:</span><span class="sxs-lookup"><span data-stu-id="c6e63-139">Use one of the following forms to indicate the character set:</span></span>  
  
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
  
 <span data-ttu-id="c6e63-140">В следующем примере показаны три управляемых определения функции **MessageBox** с атрибутами, задающими кодировку.</span><span class="sxs-lookup"><span data-stu-id="c6e63-140">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="c6e63-141">В первом определении соответствующее ключевое слово опущено, в результате чего в поле `CharSet` по умолчанию устанавливается кодировка ANSI.</span><span class="sxs-lookup"><span data-stu-id="c6e63-141">In the first definition, by its omission, the `CharSet` field defaults to the ANSI character set.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c6e63-142">См. также</span><span class="sxs-lookup"><span data-stu-id="c6e63-142">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="c6e63-143">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="c6e63-143">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="c6e63-144">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="c6e63-144">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="c6e63-145">Маршалинг данных при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="c6e63-145">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
