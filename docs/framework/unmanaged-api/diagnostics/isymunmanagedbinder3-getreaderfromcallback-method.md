---
title: Метод ISymUnmanagedBinder3::GetReaderFromCallback
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ed0097e072b34dd43876ddf23abbc1f513670ff
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776820"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a>Метод ISymUnmanagedBinder3::GetReaderFromCallback
Пользователь может реализовывать или предоставить с помощью обратного вызова, либо `IID_IDiaReadExeAtRVACallback` или `IID_IDiaReadExeAtOffsetCallback` для получения сведения о каталоге отладки из памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  
 `importer`  
 [in] Указатель на интерфейс импорта метаданных.  
  
 `fileName`  
 [in] Указатель на имя файла.  
  
 `searchPath`  
 [in] Указатель на пути поиска.  
  
 `searchPolicy`  
 [in] Значение [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) перечисления, которое указывает политику, используемую при выполнении поиска для средства чтения символов.  
  
 `callback`  
 [in] Указатель на функцию обратного вызова.  
  
 `pRetVal`  
 [out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейс.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedBinder3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
