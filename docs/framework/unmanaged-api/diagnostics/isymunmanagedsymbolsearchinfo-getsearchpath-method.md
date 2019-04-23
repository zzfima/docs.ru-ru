---
title: Метод ISymUnmanagedSymbolSearchInfo::GetSearchPath
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 649f44bd7966b9ca89d2d040b7eede662404aa0f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093557"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a>Метод ISymUnmanagedSymbolSearchInfo::GetSearchPath
Получает пути поиска.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a>Параметры  
 `pcchPath`  
 [out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения пути поиска.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
