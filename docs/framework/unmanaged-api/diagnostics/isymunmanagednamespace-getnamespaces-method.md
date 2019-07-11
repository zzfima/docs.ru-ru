---
title: Метод ISymUnmanagedNamespace::GetNamespaces
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e11886917964134a2530ae8484dba3cde5e7b61
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759369"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a>Метод ISymUnmanagedNamespace::GetNamespaces
Возвращает дочерние элементы этого пространства имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `cNameSpaces`  
 [in] Объект `ULONG32` указывает размер `namespaces` массива.  
  
 `pcNameSpaces`  
 [out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения пространства имен.  
  
 `namespaces`  
 [out] Указатель на буфер, содержащий пространства имен.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
