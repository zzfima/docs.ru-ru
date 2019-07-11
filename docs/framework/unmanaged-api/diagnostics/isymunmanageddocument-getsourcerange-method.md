---
title: Метод ISymUnmanagedDocument::GetSourceRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 981048c10be27900f011afeab55d1c5eb523f734
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776683"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a>Метод ISymUnmanagedDocument::GetSourceRange
Возвращает заданный диапазон внедренного источника в заданный буфер. Буфер должен быть достаточно большой для хранения источника.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `startLine`  
 [in] Начальная строка текущего документа.  
  
 `startColumn`  
 [in] Начальный столбец текущего документа.  
  
 `endLine`  
 [in] Последняя строка в текущем документе.  
  
 `endColumn`  
 [in] Последний столбец в текущем документе.  
  
 `cSourceBytes`  
 [in] Размер источника, в байтах.  
  
 `pcSourceBytes`  
 [out] Указатель на переменную, которая получает размер источника.  
  
 `source`  
 [out] Размер и длина указанного диапазона исходного документа, в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно.  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
