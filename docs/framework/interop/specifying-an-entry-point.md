---
title: "Specifying an Entry Point | Microsoft Docs"
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
  - "EntryPoint field"
  - "platform invoke, attribute fields"
  - "attribute fields in platform invoke, EntryPoint"
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Specifying an Entry Point
Точка входа определяет расположение функции в DLL.  В управляемом проекте исходное имя или порядковый номер точки входа целевой функции определяет эту функцию в границах взаимодействия.  Также разработчик может сопоставить точку входа с другим именем, фактически переименовывая функцию.  
  
 Ниже приведен перечень возможных причин переименования функции DLL:  
  
-   избежать использования имен API\-функций, чувствительных к регистру знаков;  
  
-   привести имена в соответствие с существующими стандартами именования;  
  
-   сделать возможным вызов функций, принимающих данные разных типов \(объявляя несколько версий одной и той же функции DLL\);  
  
-   упростить применение API\-интерфейсов, которые содержат функции версий для ANSI и Юникода.  
  
 В этом разделе показан способ переименования функции DLL в управляемом коде.  
  
## Переименование функции в Visual Basic  
 В Visual Basic для установки поля <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=fullName> используется ключевое слово **Function** в инструкции **Declare**.  В следующем примере показан базовый вариант объявления.  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
 Как показано в следующем примере, можно заменить точку входа **MessageBox** на **MsgBox**, включив в определение ключевое слово **Alias**.  В обоих примерах ключевое слово **Auto** позволяет не указывать версию кодировки для точки входа.  Дополнительные сведения о выборе кодировки см. в разделе [Задание кодировки](../../../docs/framework/interop/specifying-a-character-set.md).  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MsgBox Lib "user32.dll" _  
       Alias "MessageBox" (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## Переименование функции в C\# и C\+\+  
 Для задания функции по имени или порядковому номеру можно использовать поле <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=fullName>.  Если имя функции в определении метода совпадает с именем точки входа в DLL, явно задавать функцию с помощью поля **EntryPoint** не требуется.  В противном случае, чтобы указать имя или порядковый номер, следует использовать одну из следующих форм атрибута:  
  
```  
[DllImport("dllname", EntryPoint="Functionname")]  
[DllImport("dllname", EntryPoint="#123")]  
```  
  
 Обратите внимание, что порядковому номеру должен предшествовать знак \#.  
  
 В следующем примере показан способ замены в программном коде **MessageBoxA** на **MsgBox** с помощью поля **EntryPoint**  
  
```csharp  
using System.Runtime.InteropServices;  
  
public class Win32 {  
    [DllImport("user32.dll", EntryPoint="MessageBoxA")]  
    public static extern int MsgBox(int hWnd, String text, String caption,  
                                    uint type);  
}  
  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
  
typedef void* HWND;  
[DllImport("user32", EntryPoint="MessageBoxA")]  
extern "C" int MsgBox(HWND hWnd,  
                      String*  pText,  
                      String*  pCaption,  
                      unsigned int uType);  
```  
  
## См. также  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Platform Invoke Examples](../../../docs/framework/interop/platform-invoke-examples.md)   
 [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)