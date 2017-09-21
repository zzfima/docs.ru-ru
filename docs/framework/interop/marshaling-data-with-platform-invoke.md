---
title: "Маршалинг данных при вызове неуправляемого кода"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- platform invoke, marshaling data
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 70383e7623852935c0192e700b798a5f0ec554aa
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="marshaling-data-with-platform-invoke"></a>Маршалинг данных при вызове неуправляемого кода
Для вызова функций, экспортированных из неуправляемой библиотеки, приложению .NET Framework требуется прототип функции в управляемом коде, представляющий неуправляемую функцию. Чтобы создать прототип, который допускает вызов неуправляемого кода для правильного маршалинга данных, необходимо выполнить указанные ниже действия.  
  
-   Примените атрибут <xref:System.Runtime.InteropServices.DllImportAttribute> к статической функции или методу в управляемом коде.  
  
-   Замените неуправляемые типы данных на управляемые.  
  
 Чтобы создать эквивалентный управляемый прототип путем применения атрибута с необязательными полями и замены неуправляемых типов данных на управляемые, можно использовать документацию, предоставляемую с неуправляемой функцией. Инструкции по применению атрибута **DllImportAttribute** см. в разделе [Использование неуправляемых функций DLL](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md).  
  
 В этом разделе содержатся примеры, демонстрирующие способы создания прототипов управляемых функций для передачи аргументов и получения значений от функций, экспортируемых из неуправляемых библиотек. В примерах также демонстрируется использование атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute> и класса <xref:System.Runtime.InteropServices.Marshal> для явного маршалинга данных.  
  
## <a name="platform-invoke-data-types"></a>Типы данных в вызове неуправляемого кода  
 Ниже перечислены типы данных, используемые в функциях Win32 API (перечислены в файле Wtypes.h) и в функциях в стиле C. Многие неуправляемые библиотеки содержат функции, передающие эти типы данных в качестве параметров и возвращаемых значений. В третьем столбце представлены соответствующие встроенные типы значений .NET Framework или классы, используемые в управляемом коде. В некоторых случаях типы, перечисленные в таблице, можно заменить на типы того же размера.  
  
|Неуправляемый тип в Wtypes.h|Неуправляемый тип языка C|Имя управляемого класса|Описание|  
|--------------------------------|-------------------------------|------------------------|-----------------|  
|**HANDLE**|**void\***|<xref:System.IntPtr?displayProperty=fullName>|32 бита в 32-разрядных операционных системах Windows, 64 бита в 64-разрядных операционных системах Windows.|  
|**BYTE**|**unsigned char**|<xref:System.Byte?displayProperty=fullName>|8 бит|  
|**SHORT**|**short**|<xref:System.Int16?displayProperty=fullName>|16 бит|  
|**WORD**|**unsigned short**|<xref:System.UInt16?displayProperty=fullName>|16 бит|  
|**INT**|**int**|<xref:System.Int32?displayProperty=fullName>|32 бита|  
|**UINT**|**unsigned int**|<xref:System.UInt32?displayProperty=fullName>|32 бита|  
|**LONG**|**long**|<xref:System.Int32?displayProperty=fullName>|32 бита|  
|**BOOL**|**long**|<xref:System.Byte>|32 бита|  
|**DWORD**|**unsigned long**|<xref:System.UInt32?displayProperty=fullName>|32 бита|  
|**ULONG**|**unsigned long**|<xref:System.UInt32?displayProperty=fullName>|32 бита|  
|**CHAR**|**char**|<xref:System.Char?displayProperty=fullName>|В кодировке ANSI.|  
|**WCHAR**|**wchar_t**|<xref:System.Char?displayProperty=fullName>|В кодировке Юникод.|  
|**LPSTR**|**char\***|<xref:System.String?displayProperty=fullName> или <xref:System.Text.StringBuilder?displayProperty=fullName>|В кодировке ANSI.|  
|**LPCSTR**|**Const char\***|<xref:System.String?displayProperty=fullName> или <xref:System.Text.StringBuilder?displayProperty=fullName>|В кодировке ANSI.|  
|**LPWSTR**|**wchar_t\***|<xref:System.String?displayProperty=fullName> или <xref:System.Text.StringBuilder?displayProperty=fullName>|В кодировке Юникод.|  
|**LPCWSTR**|**Const wchar_t\***|<xref:System.String?displayProperty=fullName> или <xref:System.Text.StringBuilder?displayProperty=fullName>|В кодировке Юникод.|  
|**FLOAT**|**Float**|<xref:System.Single?displayProperty=fullName>|32 бита|  
|**DOUBLE**|**Double**|<xref:System.Double?displayProperty=fullName>|64 бита|  
  
 Соответствующие типы в [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# и C++ см. в разделе [Общие сведения о библиотеке классов .NET Framework](../../../docs/standard/class-library-overview.md).  
  
## <a name="pinvokelibdll"></a>PinvokeLib.dll  
 В примере кода ниже определяются функции библиотеки, предоставляемые Pinvoke.dll. Многие из примеров, описанных в этом разделе, вызывают эту библиотеку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]  
  
 [!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]

