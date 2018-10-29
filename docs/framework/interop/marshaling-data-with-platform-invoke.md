---
title: Маршалинг данных при вызове неуправляемого кода
ms.date: 07/31/2018
dev_langs:
- cpp
helpviewer_keywords:
- platform invoke, marshaling data
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae8fbb47986e5baaecb919ce79ae384a8427737a
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "48850482"
---
# <a name="marshaling-data-with-platform-invoke"></a>Маршалинг данных при вызове неуправляемого кода
Для вызова функций, экспортированных из неуправляемой библиотеки, приложению .NET Framework требуется прототип функции в управляемом коде, представляющий неуправляемую функцию. Чтобы создать прототип, который допускает вызов неуправляемого кода для правильного маршалинга данных, необходимо выполнить указанные ниже действия.  
  
-   Примените атрибут <xref:System.Runtime.InteropServices.DllImportAttribute> к статической функции или методу в управляемом коде.  
  
-   Замените неуправляемые типы данных на управляемые.  
  
 Чтобы создать эквивалентный управляемый прототип путем применения атрибута с необязательными полями и замены неуправляемых типов данных на управляемые, можно использовать документацию, предоставляемую с неуправляемой функцией. Инструкции по применению атрибута **DllImportAttribute** см. в разделе [Использование неуправляемых функций DLL](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md).  
  
 В этом разделе содержатся примеры, демонстрирующие способы создания прототипов управляемых функций для передачи аргументов и получения значений от функций, экспортируемых из неуправляемых библиотек. В примерах также демонстрируется использование атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute> и класса <xref:System.Runtime.InteropServices.Marshal> для явного маршалинга данных.  
  
## <a name="platform-invoke-data-types"></a>Типы данных в вызове неуправляемого кода  
 Ниже перечислены типы данных, используемые в функциях Win32 API (перечислены в файле Wtypes.h) и в функциях в стиле C. Многие неуправляемые библиотеки содержат функции, передающие эти типы данных в качестве параметров и возвращаемых значений. В третьем столбце представлены соответствующие встроенные типы значений .NET Framework или классы, используемые в управляемом коде. В некоторых случаях типы, перечисленные в таблице, можно заменить на типы того же размера.  
  
|Неуправляемый тип в Wtypes.h|Неуправляемый тип языка C|Имя управляемого класса|Описание:|  
|--------------------------------|-------------------------------|------------------------|-----------------|  
|**VOID**|**void**|<xref:System.Void?displayProperty=nameWithType>|Применяется к функции, которая не возвращает значение.|
|**HANDLE**|**void \***|<xref:System.IntPtr?displayProperty=nameWithType>|32 бита в 32-разрядных операционных системах Windows, 64 бита в 64-разрядных операционных системах Windows.|  
|**BYTE**|**unsigned char**|<xref:System.Byte?displayProperty=nameWithType>|8 бит|  
|**SHORT**|**short**|<xref:System.Int16?displayProperty=nameWithType>|16 бит|  
|**WORD**|**unsigned short**|<xref:System.UInt16?displayProperty=nameWithType>|16 бит|  
|**INT**|**int**|<xref:System.Int32?displayProperty=nameWithType>|32 бита|  
|**UINT**|**unsigned int**|<xref:System.UInt32?displayProperty=nameWithType>|32 бита|  
|**LONG**|**long**|<xref:System.Int32?displayProperty=nameWithType>|32 бита|  
|**BOOL**|**long**|<xref:System.Byte>|32 бита|  
|**DWORD**|**unsigned long**|<xref:System.UInt32?displayProperty=nameWithType>|32 бита|  
|**ULONG**|**unsigned long**|<xref:System.UInt32?displayProperty=nameWithType>|32 бита|  
|**CHAR**|**char**|<xref:System.Char?displayProperty=nameWithType>|В кодировке ANSI.|  
|**WCHAR**|**wchar_t**|<xref:System.Char?displayProperty=nameWithType>|В кодировке Юникод.|  
|**LPSTR**|**char &ast;**|<xref:System.String?displayProperty=nameWithType> или <xref:System.Text.StringBuilder?displayProperty=nameWithType>|В кодировке ANSI.|  
|**LPCSTR**|**Const char &ast;**|<xref:System.String?displayProperty=nameWithType> или <xref:System.Text.StringBuilder?displayProperty=nameWithType>|В кодировке ANSI.|  
|**LPWSTR**|**wchar_t &ast;**|<xref:System.String?displayProperty=nameWithType> или <xref:System.Text.StringBuilder?displayProperty=nameWithType>|В кодировке Юникод.|  
|**LPCWSTR**|**Const wchar_t &ast;**|<xref:System.String?displayProperty=nameWithType> или <xref:System.Text.StringBuilder?displayProperty=nameWithType>|В кодировке Юникод.|  
|**FLOAT**|**Float**|<xref:System.Single?displayProperty=nameWithType>|32 бита|  
|**DOUBLE**|**Double**|<xref:System.Double?displayProperty=nameWithType>|64 бита|  
  
 Соответствующие типы в [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# и C++ см. в разделе [Общие сведения о библиотеке классов .NET Framework](../../../docs/standard/class-library-overview.md).  
  
## <a name="pinvokelibdll"></a>PinvokeLib.dll  
 В примере кода ниже определяются функции библиотеки, предоставляемые Pinvoke.dll. Многие из примеров, описанных в этом разделе, вызывают эту библиотеку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]  
  
 [!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]
