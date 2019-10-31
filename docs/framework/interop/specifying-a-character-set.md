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
ms.openlocfilehash: 0db1cd8d75b45f6d718168793c873e5867028269
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125178"
---
# <a name="specifying-a-character-set"></a><span data-ttu-id="25c93-102">Определение кодировки</span><span class="sxs-lookup"><span data-stu-id="25c93-102">Specifying a Character Set</span></span>
<span data-ttu-id="25c93-103">Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> управляет маршалингом строк и определяет, каким образом при вызове неуправляемого кода будут обнаруживаться имена функций в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="25c93-103">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="25c93-104">В этом разделе описываются оба механизма.</span><span class="sxs-lookup"><span data-stu-id="25c93-104">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="25c93-105">Некоторые API экспортируют две версии функций, которые принимают строковые аргументы: обычные (ANSI) и двухбайтовые (Юникод).</span><span class="sxs-lookup"><span data-stu-id="25c93-105">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="25c93-106">Например, API Windows включает следующие имена точек входа для функции **MessageBox**:</span><span class="sxs-lookup"><span data-stu-id="25c93-106">The Windows API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
- <span data-ttu-id="25c93-107">**MessageBoxA**</span><span class="sxs-lookup"><span data-stu-id="25c93-107">**MessageBoxA**</span></span>  
  
     <span data-ttu-id="25c93-108">Обеспечивает форматирование однобайтовых символов ANSI и имеет суффикс "A" в имени точки входа.</span><span class="sxs-lookup"><span data-stu-id="25c93-108">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="25c93-109">При вызове **MessageBoxA** строки всегда маршалируются в формате ANSI.</span><span class="sxs-lookup"><span data-stu-id="25c93-109">Calls to **MessageBoxA** always marshal strings in ANSI format.</span></span>  
  
- <span data-ttu-id="25c93-110">**MessageBoxW**</span><span class="sxs-lookup"><span data-stu-id="25c93-110">**MessageBoxW**</span></span>  
  
     <span data-ttu-id="25c93-111">Обеспечивает форматирование двухбайтовых символов Юникода и имеет суффикс "W" в имени точки входа.</span><span class="sxs-lookup"><span data-stu-id="25c93-111">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="25c93-112">При вызове **MessageBoxW** строки всегда маршалируются в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="25c93-112">Calls to **MessageBoxW** always marshal strings in Unicode format.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="25c93-113">Маршалинг строк и сопоставление имен</span><span class="sxs-lookup"><span data-stu-id="25c93-113">String Marshaling and Name Matching</span></span>  
 <span data-ttu-id="25c93-114">Поле `CharSet` принимает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="25c93-114">The `CharSet` field accepts the following values:</span></span>  
  
 <span data-ttu-id="25c93-115"><xref:System.Runtime.InteropServices.CharSet.Ansi> (значение по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="25c93-115"><xref:System.Runtime.InteropServices.CharSet.Ansi> (default value)</span></span>  
  
- <span data-ttu-id="25c93-116">Маршалинг строк</span><span class="sxs-lookup"><span data-stu-id="25c93-116">String marshaling</span></span>  
  
     <span data-ttu-id="25c93-117">При вызове неуправляемого кода выполняется маршалинг строк из соответствующего управляемого формата (Юникод) в формат ANSI.</span><span class="sxs-lookup"><span data-stu-id="25c93-117">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
- <span data-ttu-id="25c93-118">Сопоставление имен</span><span class="sxs-lookup"><span data-stu-id="25c93-118">Name matching</span></span>  
  
     <span data-ttu-id="25c93-119">Если поле <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> имеет значение `true` (значение по умолчанию в Visual Basic), при вызове неуправляемого кода осуществляется поиск только указанного имени.</span><span class="sxs-lookup"><span data-stu-id="25c93-119">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is `true`, as it is by default in Visual Basic, platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="25c93-120">Например, если указать **MessageBox**, при вызове неуправляемого кода будет выполнен поиск **MessageBox**, который может завершиться сбоем из-за невозможности найти точное совпадение.</span><span class="sxs-lookup"><span data-stu-id="25c93-120">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="25c93-121">Если поле `ExactSpelling` имеет значение `false` (по умолчанию для C++ и C#), при вызове неуправляемого кода выполняется поиск сначала неуправляемого псевдонима (**MessageBox**), а затем, если неуправляемый псевдоним не найден, управляемого имени (**MessageBoxA**).</span><span class="sxs-lookup"><span data-stu-id="25c93-121">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="25c93-122">Обратите внимание, что принципы сопоставления имен ANSI и Юникода различаются.</span><span class="sxs-lookup"><span data-stu-id="25c93-122">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Unicode>  
  
- <span data-ttu-id="25c93-123">Маршалинг строк</span><span class="sxs-lookup"><span data-stu-id="25c93-123">String marshaling</span></span>  
  
     <span data-ttu-id="25c93-124">При вызове неуправляемого кода строки копируются из соответствующего управляемого формата (Юникод) в формат Юникода.</span><span class="sxs-lookup"><span data-stu-id="25c93-124">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
- <span data-ttu-id="25c93-125">Сопоставление имен</span><span class="sxs-lookup"><span data-stu-id="25c93-125">Name matching</span></span>  
  
     <span data-ttu-id="25c93-126">Если поле `ExactSpelling` имеет значение `true` (значение по умолчанию в Visual Basic), при вызове неуправляемого кода осуществляется поиск только указанного имени.</span><span class="sxs-lookup"><span data-stu-id="25c93-126">When the `ExactSpelling` field is `true`, as it is by default in Visual Basic, platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="25c93-127">Например, если указать **MessageBox**, при вызове неуправляемого кода будет выполнен поиск **MessageBox**, который может завершиться сбоем из-за невозможности найти точное совпадение.</span><span class="sxs-lookup"><span data-stu-id="25c93-127">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="25c93-128">Если поле `ExactSpelling` имеет значение `false` (по умолчанию для C++ и C#), при вызове неуправляемого кода выполняется поиск сначала управляемого имени (**MessageBoxW**), а затем, если управляемое имя не найдено, неуправляемого псевдонима (**MessageBox**).</span><span class="sxs-lookup"><span data-stu-id="25c93-128">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="25c93-129">Обратите внимание, что принципы сопоставления имен Юникода и ANSI различаются.</span><span class="sxs-lookup"><span data-stu-id="25c93-129">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Auto>  
  
- <span data-ttu-id="25c93-130">При вызове неуправляемого кода во время выполнения осуществляется выбор между форматами ANSI и Юникода в соответствии с целевой платформой.</span><span class="sxs-lookup"><span data-stu-id="25c93-130">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specifying-a-character-set-in-visual-basic"></a><span data-ttu-id="25c93-131">Определение кодировки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="25c93-131">Specifying a Character Set in Visual Basic</span></span>  
 <span data-ttu-id="25c93-132">В следующем примере функция **MessageBox** объявляется три раза с разными кодировками.</span><span class="sxs-lookup"><span data-stu-id="25c93-132">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="25c93-133">В Visual Basic можно указать поведение кодировки, добавив ключевое слово **Ansi**, **Unicode** или **Auto** в оператор объявления.</span><span class="sxs-lookup"><span data-stu-id="25c93-133">You can specify character-set behavior in Visual Basic by adding the **Ansi**, **Unicode**, or **Auto** keyword to the declaration statement.</span></span>  
  
 <span data-ttu-id="25c93-134">Если опустить ключевое слово кодировки, как показано в первом операторе объявления, в поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> по умолчанию будет задана кодировка ANSI.</span><span class="sxs-lookup"><span data-stu-id="25c93-134">If you omit the character-set keyword, as is done in the first declaration statement, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span> <span data-ttu-id="25c93-135">Во втором и третьем операторе в этом примере кодировка задается явно с использованием ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="25c93-135">The second and third statements in the example explicitly specify a character set with a keyword.</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Function MessageBoxA Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Declare Unicode Function MessageBoxW Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="specifying-a-character-set-in-c-and-c"></a><span data-ttu-id="25c93-136">Определение кодировки в C# и C++</span><span class="sxs-lookup"><span data-stu-id="25c93-136">Specifying a Character Set in C# and C++</span></span>  
 <span data-ttu-id="25c93-137">Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> определяет базовую кодировку как ANSI или Юникод.</span><span class="sxs-lookup"><span data-stu-id="25c93-137">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="25c93-138">Кодировка определяет порядок маршалинга строковых аргументов в метод.</span><span class="sxs-lookup"><span data-stu-id="25c93-138">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="25c93-139">Чтобы указать кодировку, используйте одну из следующих форм:</span><span class="sxs-lookup"><span data-stu-id="25c93-139">Use one of the following forms to indicate the character set:</span></span>  
  
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
  
 <span data-ttu-id="25c93-140">В следующем примере показаны три управляемых определения функции **MessageBox** с атрибутами, задающими кодировку.</span><span class="sxs-lookup"><span data-stu-id="25c93-140">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="25c93-141">В первом определении соответствующее ключевое слово опущено, в результате чего в поле `CharSet` по умолчанию устанавливается кодировка ANSI.</span><span class="sxs-lookup"><span data-stu-id="25c93-141">In the first definition, by its omission, the `CharSet` field defaults to the ANSI character set.</span></span>  
  
```csharp  
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
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
  
## <a name="see-also"></a><span data-ttu-id="25c93-142">См. также</span><span class="sxs-lookup"><span data-stu-id="25c93-142">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="25c93-143">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="25c93-143">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="25c93-144">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="25c93-144">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="25c93-145">Маршалинг данных при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="25c93-145">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
