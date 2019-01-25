---
title: Метод ISymUnmanagedScope::GetLocalCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 809b9033c784954374065a901f34f7542f41e7ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549946"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a>Метод ISymUnmanagedScope::GetLocalCount
Возвращает число локальных переменных, определенных в данной области.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pRetVal`  
 [out] Указатель на `ULONG32` , Получает число локальных переменных.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
