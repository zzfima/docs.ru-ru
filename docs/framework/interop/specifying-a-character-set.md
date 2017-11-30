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
ms.openlocfilehash: 3e97c640472156c1a47ad125bffeaf39b8eb0762
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="specifying-a-character-set"></a>Определение кодировки
Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> управляет маршалингом строк и определяет, каким образом при вызове неуправляемого кода будут обнаруживаться имена функций в библиотеке DLL. В этом разделе описываются оба механизма.  
  
 Некоторые API экспортируют две версии функций, которые принимают строковые аргументы: обычные (ANSI) и двухбайтовые (Юникод). Например, API Win32 включает следующие имена точек входа для функции **MessageBox**:  
  
-   **MessageBoxA**  
  
     Обеспечивает форматирование однобайтовых символов ANSI и имеет суффикс "A" в имени точки входа. При вызове **MessageBoxA** строки всегда маршалируются в формате ANSI, что характерно для платформ Windows 95 и Windows 98.  
  
-   **MessageBoxW**  
  
     Обеспечивает форматирование двухбайтовых символов Юникода и имеет суффикс "W" в имени точки входа. При вызове **MessageBoxW** строки всегда маршалируются в формате Юникода, что характерно для платформ Windows NT, Windows 2000 и Windows XP.  
  
## <a name="string-marshaling-and-name-matching"></a>Маршалинг строк и сопоставление имен  
 Поле **CharSet** принимает следующие значения:  
  
 **CharSet.Ansi** (значение по умолчанию)  
  
-   Маршалинг строк  
  
     При вызове неуправляемого кода выполняется маршалинг строк из соответствующего управляемого формата (Юникод) в формат ANSI.  
  
-   Сопоставление имен  
  
     Если поле <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> имеет значение **true** (по умолчанию для [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]), при вызове неуправляемого кода осуществляется поиск только указанного имени. Например, если указать **MessageBox**, при вызове неуправляемого кода будет выполнен поиск **MessageBox**, который может завершиться сбоем из-за невозможности найти точное совпадение.  
  
     Если поле **ExactSpelling** имеет значение **false** (по умолчанию для C++ и C#), при вызове неуправляемого кода выполняется поиск сначала неуправляемого псевдонима (**MessageBox**), а затем, если неуправляемый псевдоним не найден, управляемого имени (**MessageBoxA**). Обратите внимание, что принципы сопоставления имен ANSI и Юникода различаются.  
  
 **CharSet.Unicode**  
  
-   Маршалинг строк  
  
     При вызове неуправляемого кода строки копируются из соответствующего управляемого формата (Юникод) в формат Юникода.  
  
-   Сопоставление имен  
  
     Если поле **ExactSpelling** имеет значение **true** (по умолчанию для [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]), при вызове неуправляемого кода осуществляется поиск только указанного имени. Например, если указать **MessageBox**, при вызове неуправляемого кода будет выполнен поиск **MessageBox**, который может завершиться сбоем из-за невозможности найти точное совпадение.  
  
     Если поле **ExactSpelling** имеет значение **false** (по умолчанию для C++ и C#), при вызове неуправляемого кода выполняется поиск сначала управляемого имени (**MessageBoxW**), а затем, если управляемое имя не найдено, неуправляемого псевдонима (**MessageBox**). Обратите внимание, что принципы сопоставления имен Юникода и ANSI различаются.  
  
 **CharSet.Auto**  
  
-   При вызове неуправляемого кода во время выполнения осуществляется выбор между форматами ANSI и Юникода в соответствии с целевой платформой.  
  
## <a name="specifying-a-character-set-in-visual-basic"></a>Определение кодировки в Visual Basic  
 В следующем примере функция **MessageBox** объявляется три раза с разными кодировками. В Visual Basic можно указать поведение кодировки, добавив ключевое слово **Ansi**, **Unicode** или **Auto** в оператор объявления.  
  
 Если опустить ключевое слово кодировки, как показано в первом операторе объявления, в поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> по умолчанию будет задана кодировка ANSI. Во втором и третьем операторе в этом примере кодировка задается явно с использованием ключевого слова.  
  
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
  
## <a name="specifying-a-character-set-in-c-and-c"></a>Определение кодировки в C# и C++  
 Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> определяет базовую кодировку как ANSI или Юникод. Кодировка определяет порядок маршалинга строковых аргументов в метод. Чтобы указать кодировку, используйте одну из следующих форм:  
  
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
  
 В следующем примере показаны три управляемых определения функции **MessageBox** с атрибутами, задающими кодировку. В первом определении соответствующее ключевое слово опущено, в результате чего в поле **CharSet** по умолчанию устанавливается кодировка ANSI.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [Создание прототипов в управляемом коде](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [Примеры вызовов неуправляемого кода](../../../docs/framework/interop/platform-invoke-examples.md)  
 [Маршалинг данных при вызове неуправляемого кода](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
