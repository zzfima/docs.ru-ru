---
title: "Определение кодировки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: afb2ae519b4a3d52c590f050ba728286898373ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="specifying-a-character-set"></a><span data-ttu-id="7ec99-102">Определение кодировки</span><span class="sxs-lookup"><span data-stu-id="7ec99-102">Specifying a Character Set</span></span>
<span data-ttu-id="7ec99-103">Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> управляет маршалингом строк и определяет, каким образом при вызове неуправляемого кода будут обнаруживаться имена функций в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="7ec99-103">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="7ec99-104">В этом разделе описываются оба механизма.</span><span class="sxs-lookup"><span data-stu-id="7ec99-104">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="7ec99-105">Некоторые API экспортируют две версии функций, которые принимают строковые аргументы: обычные (ANSI) и двухбайтовые (Юникод).</span><span class="sxs-lookup"><span data-stu-id="7ec99-105">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="7ec99-106">Например, API Win32 включает следующие имена точек входа для функции **MessageBox**:</span><span class="sxs-lookup"><span data-stu-id="7ec99-106">The Win32 API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
-   <span data-ttu-id="7ec99-107">**MessageBoxA**</span><span class="sxs-lookup"><span data-stu-id="7ec99-107">**MessageBoxA**</span></span>  
  
     <span data-ttu-id="7ec99-108">Обеспечивает форматирование однобайтовых символов ANSI и имеет суффикс "A" в имени точки входа.</span><span class="sxs-lookup"><span data-stu-id="7ec99-108">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="7ec99-109">При вызове **MessageBoxA** строки всегда маршалируются в формате ANSI, что характерно для платформ Windows 95 и Windows 98.</span><span class="sxs-lookup"><span data-stu-id="7ec99-109">Calls to **MessageBoxA** always marshal strings in ANSI format, as is common on Windows 95 and Windows 98 platforms.</span></span>  
  
-   <span data-ttu-id="7ec99-110">**MessageBoxW**</span><span class="sxs-lookup"><span data-stu-id="7ec99-110">**MessageBoxW**</span></span>  
  
     <span data-ttu-id="7ec99-111">Обеспечивает форматирование двухбайтовых символов Юникода и имеет суффикс "W" в имени точки входа.</span><span class="sxs-lookup"><span data-stu-id="7ec99-111">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="7ec99-112">При вызове **MessageBoxW** строки всегда маршалируются в формате Юникода, что характерно для платформ Windows NT, Windows 2000 и Windows XP.</span><span class="sxs-lookup"><span data-stu-id="7ec99-112">Calls to **MessageBoxW** always marshal strings in Unicode format, as is common on Windows NT, Windows 2000, and Windows XP platforms.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="7ec99-113">Маршалинг строк и сопоставление имен</span><span class="sxs-lookup"><span data-stu-id="7ec99-113">String Marshaling and Name Matching</span></span>  
 <span data-ttu-id="7ec99-114">Поле **CharSet** принимает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7ec99-114">The **CharSet** field accepts the following values:</span></span>  
  
 <span data-ttu-id="7ec99-115">**CharSet.Ansi** (значение по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7ec99-115">**CharSet.Ansi** (default value)</span></span>  
  
-   <span data-ttu-id="7ec99-116">Маршалинг строк</span><span class="sxs-lookup"><span data-stu-id="7ec99-116">String marshaling</span></span>  
  
     <span data-ttu-id="7ec99-117">При вызове неуправляемого кода выполняется маршалинг строк из соответствующего управляемого формата (Юникод) в формат ANSI.</span><span class="sxs-lookup"><span data-stu-id="7ec99-117">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
-   <span data-ttu-id="7ec99-118">Сопоставление имен</span><span class="sxs-lookup"><span data-stu-id="7ec99-118">Name matching</span></span>  
  
     <span data-ttu-id="7ec99-119">Если поле <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> имеет значение **true** (по умолчанию для [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]), при вызове неуправляемого кода осуществляется поиск только указанного имени.</span><span class="sxs-lookup"><span data-stu-id="7ec99-119">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is **true**, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="7ec99-120">Например, если указать **MessageBox**, при вызове неуправляемого кода будет выполнен поиск **MessageBox**, который может завершиться сбоем из-за невозможности найти точное совпадение.</span><span class="sxs-lookup"><span data-stu-id="7ec99-120">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="7ec99-121">Если поле **ExactSpelling** имеет значение **false** (по умолчанию для C++ и C#), при вызове неуправляемого кода выполняется поиск сначала неуправляемого псевдонима (**MessageBox**), а затем, если неуправляемый псевдоним не найден, управляемого имени (**MessageBoxA**).</span><span class="sxs-lookup"><span data-stu-id="7ec99-121">When the **ExactSpelling** field is **false**, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="7ec99-122">Обратите внимание, что принципы сопоставления имен ANSI и Юникода различаются.</span><span class="sxs-lookup"><span data-stu-id="7ec99-122">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <span data-ttu-id="7ec99-123">**CharSet.Unicode**</span><span class="sxs-lookup"><span data-stu-id="7ec99-123">**CharSet.Unicode**</span></span>  
  
-   <span data-ttu-id="7ec99-124">Маршалинг строк</span><span class="sxs-lookup"><span data-stu-id="7ec99-124">String marshaling</span></span>  
  
     <span data-ttu-id="7ec99-125">При вызове неуправляемого кода строки копируются из соответствующего управляемого формата (Юникод) в формат Юникода.</span><span class="sxs-lookup"><span data-stu-id="7ec99-125">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
-   <span data-ttu-id="7ec99-126">Сопоставление имен</span><span class="sxs-lookup"><span data-stu-id="7ec99-126">Name matching</span></span>  
  
     <span data-ttu-id="7ec99-127">Если поле **ExactSpelling** имеет значение **true** (по умолчанию для [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]), при вызове неуправляемого кода осуществляется поиск только указанного имени.</span><span class="sxs-lookup"><span data-stu-id="7ec99-127">When the **ExactSpelling** field is **true**, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="7ec99-128">Например, если указать **MessageBox**, при вызове неуправляемого кода будет выполнен поиск **MessageBox**, который может завершиться сбоем из-за невозможности найти точное совпадение.</span><span class="sxs-lookup"><span data-stu-id="7ec99-128">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="7ec99-129">Если поле **ExactSpelling** имеет значение **false** (по умолчанию для C++ и C#), при вызове неуправляемого кода выполняется поиск сначала управляемого имени (**MessageBoxW**), а затем, если управляемое имя не найдено, неуправляемого псевдонима (**MessageBox**).</span><span class="sxs-lookup"><span data-stu-id="7ec99-129">When the **ExactSpelling** field is **false**, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="7ec99-130">Обратите внимание, что принципы сопоставления имен Юникода и ANSI различаются.</span><span class="sxs-lookup"><span data-stu-id="7ec99-130">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <span data-ttu-id="7ec99-131">**CharSet.Auto**</span><span class="sxs-lookup"><span data-stu-id="7ec99-131">**CharSet.Auto**</span></span>  
  
-   <span data-ttu-id="7ec99-132">При вызове неуправляемого кода во время выполнения осуществляется выбор между форматами ANSI и Юникода в соответствии с целевой платформой.</span><span class="sxs-lookup"><span data-stu-id="7ec99-132">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specifying-a-character-set-in-visual-basic"></a><span data-ttu-id="7ec99-133">Определение кодировки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ec99-133">Specifying a Character Set in Visual Basic</span></span>  
 <span data-ttu-id="7ec99-134">В следующем примере функция **MessageBox** объявляется три раза с разными кодировками.</span><span class="sxs-lookup"><span data-stu-id="7ec99-134">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="7ec99-135">В Visual Basic можно указать поведение кодировки, добавив ключевое слово **Ansi**, **Unicode** или **Auto** в оператор объявления.</span><span class="sxs-lookup"><span data-stu-id="7ec99-135">You can specify character-set behavior in Visual Basic by adding the **Ansi**, **Unicode**, or **Auto** keyword to the declaration statement.</span></span>  
  
 <span data-ttu-id="7ec99-136">Если опустить ключевое слово кодировки, как показано в первом операторе объявления, в поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> по умолчанию будет задана кодировка ANSI.</span><span class="sxs-lookup"><span data-stu-id="7ec99-136">If you omit the character-set keyword, as is done in the first declaration statement, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span> <span data-ttu-id="7ec99-137">Во втором и третьем операторе в этом примере кодировка задается явно с использованием ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="7ec99-137">The second and third statements in the example explicitly specify a character set with a keyword.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
   Declare Function MessageBoxA Lib "user32.dll"(ByVal hWnd As Integer, _  
       ByVal txt As String, ByVal caption As String, _  
       ByVal Typ As Integer) As Integer  
  
   Declare Unicode Function MessageBoxW Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
  
   Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="specifying-a-character-set-in-c-and-c"></a><span data-ttu-id="7ec99-138">Определение кодировки в C# и C++</span><span class="sxs-lookup"><span data-stu-id="7ec99-138">Specifying a Character Set in C# and C++</span></span>  
 <span data-ttu-id="7ec99-139">Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> определяет базовую кодировку как ANSI или Юникод.</span><span class="sxs-lookup"><span data-stu-id="7ec99-139">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="7ec99-140">Кодировка определяет порядок маршалинга строковых аргументов в метод.</span><span class="sxs-lookup"><span data-stu-id="7ec99-140">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="7ec99-141">Чтобы указать кодировку, используйте одну из следующих форм:</span><span class="sxs-lookup"><span data-stu-id="7ec99-141">Use one of the following forms to indicate the character set:</span></span>  
  
```csharp  
[DllImport("dllname", CharSet=CharSet.Ansi)]  
[DllImport("dllname", CharSet=CharSet.Unicode)]  
[DllImport("dllname", CharSet=CharSet.Auto)]  
```  
  
```cpp  
[DllImport("dllname", CharSet=CharSet::Ansi)]  
[DllImport("dllname", CharSet=CharSet::Unicode)]  
[DllImport("dllname", CharSet=CharSet::Auto)]  
```  
  
 <span data-ttu-id="7ec99-142">В следующем примере показаны три управляемых определения функции **MessageBox** с атрибутами, задающими кодировку.</span><span class="sxs-lookup"><span data-stu-id="7ec99-142">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="7ec99-143">В первом определении соответствующее ключевое слово опущено, в результате чего в поле **CharSet** по умолчанию устанавливается кодировка ANSI.</span><span class="sxs-lookup"><span data-stu-id="7ec99-143">In the first definition, by its omission, the **CharSet** field defaults to the ANSI character set.</span></span>  
  
```csharp  
[DllImport("user32.dll")]  
    public static extern int MessageBoxA(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Unicode)]  
    public static extern int MessageBoxW(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Auto)]  
    public static extern int MessageBox(int hWnd, String text,   
        String caption, uint type);  
```  
  
```cpp  
typedef void* HWND;  
  
//Can use MessageBox or MessageBoxA.  
[DllImport("user32")]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Can use MessageBox or MessageBoxW.  
[DllImport("user32", CharSet=CharSet::Unicode)]  
extern "C" int MessageBoxW(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Must use MessageBox.  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ec99-144">См. также</span><span class="sxs-lookup"><span data-stu-id="7ec99-144">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [<span data-ttu-id="7ec99-145">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="7ec99-145">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="7ec99-146">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="7ec99-146">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="7ec99-147">Маршалинг данных при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="7ec99-147">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
