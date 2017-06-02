---
title: "Specifying a Character Set | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "platform invoke, attribute fields"
  - "attribute fields in platform invoke, CharSet"
  - "CharSet field"
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Specifying a Character Set
Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> управляет маршалингом строк и определяет, как вызов неуправляемого кода находит имена функций в библиотеке DLL.  В этом разделе описываются оба назначения поля.  
  
 Некоторые интерфейсы API экспортируют две версии функций, которые принимают строковые аргументы: узкую \(ANSI\) и широкую \(Юникод\).  Например, интерфейс Win32 API для функции **MessageBox** содержит следующие имена точек входа:  
  
-   **MessageBoxA**  
  
     Обеспечивает форматирование с использованием 1\-байтовых символов ANSI, на что указывает буква "A", добавляемая в конец имени точки входа.  При вызовах **MessageBoxA** маршалинг строк всегда выполняется в формате ANSI, который обычно применяется в платформах Windows 98 и Windows 95.  
  
-   **MessageBoxW**  
  
     Обеспечивает форматирование с использованием 2\-байтовых символов Юникода, на что указывает буква "W", добавляемая в конец имени точки входа.  При вызовах **MessageBoxW** маршалинг строк всегда выполняется в формате Юникода, который обычно применяется в платформах Windows NT, Windows 2000 и Windows XP.  
  
## Маршалинг строк и совпадение имен  
 Поле **CharSet** может принимать следующие значения:  
  
 **CharSet.Ansi** \(значение по умолчанию\)  
  
-   Маршалинг строк  
  
     Вызов неуправляемого кода выполняет маршалинг строк из соответствующего управляемого формата \(Юникод\) в формат ANSI.  
  
-   Совпадение имен  
  
     Когда значение поля <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=fullName> равно **true**, как установлено по умолчанию в [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], вызов неуправляемого кода выполняет поиск только заданного разработчиком имени.  Например, если указано имя **MessageBox**, вызов неуправляемого кода ищет именно **MessageBox**. Если найти точное посимвольное совпадение не удается, возникает сбой.  
  
     Когда значение поля **ExactSpelling** равно **false**, являющееся значением по умолчанию в C\+\+ и C\#, вызов неуправляемого кода сначала ищет точный псевдоним \(**MessageBox**\), а затем неточное имя \(**MessageBoxA**\), если найти точный псевдоним не удалось.  Следует учитывать, что критерии совпадения имен в формате ANSI отличается от критериев совпадения имен в формате Юникода.  
  
 **CharSet.Unicode**  
  
-   Маршалинг строк  
  
     Вызов неуправляемого кода копирует строки из соответствующего управляемого формата \(Юникод\) в формат Юникода.  
  
-   Совпадение имен  
  
     Когда значение поля **ExactSpelling** равно **true**, являющееся значением по умолчанию в [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], вызов неуправляемого кода выполняет поиск только заданного разработчиком имени.  Например, если указано **MessageBox**, вызов неуправляемого кода ищет именно **MessageBox**. Если найти точное посимвольное совпадение не удается, возникает сбой.  
  
     Когда значение поля **ExactSpelling** равно **false**, являющееся значением по умолчанию в C\+\+ и C\#, вызов неуправляемого кода сначала выполняет поиск искаженного имени \(**MessageBoxW**\), а затем поиск точного имени \(**MessageBox**\), если искаженное имя не найдено.  Следует учитывать, что критерии совпадения имен в формате Юникода отличается от критериев совпадения имен в формате ANSI.  
  
 **CharSet.Auto**  
  
-   Вызов неуправляемого кода выбирает между форматами ANSI и Юникод во время выполнения в соответствии с целевой платформой.  
  
## Задание кодировки в Visual Basic  
 В следующем примере функция **MessageBox** объявляется три раза с разными режимами работы с кодировками.  В Visual Basic режим работы с кодировками можно задать, добавляя к инструкции объявления ключевое слово **Ansi**, **Unicode** или **Auto**.  
  
 Если ключевое слово кодировки опущено, как в случае первой инструкции объявления, поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> по умолчанию определять кодировку ANSI.  Во второй и третьей инструкциях примера кодировка явно указана с помощью ключевого слова.  
  
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
  
## Задание кодировки в C\# и C\+\+  
 Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> определяет базовую кодировку как ANSI или Юникод.  Кодировка определяет способ выполнения маршалинга строковых аргументов.  Для указания кодировки используется один из следующих вариантов инструкции:  
  
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
  
 В следующем примере показаны три управляемых определения функции **MessageBox** с атрибутами, задающими кодировку.  В первом определении, в котором значение поля **CharSet** опущено, по умолчанию используется кодировка ANSI.  
  
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
  
## См. также  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Platform Invoke Examples](../../../docs/framework/interop/platform-invoke-examples.md)   
 [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)