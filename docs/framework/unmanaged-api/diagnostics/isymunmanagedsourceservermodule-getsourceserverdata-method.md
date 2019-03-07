---
title: Метод ISymUnmanagedSourceServerModule::GetSourceServerData
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69e83a5ff489881938c1e8410f765fd63f3b5d84
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479445"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a>Метод ISymUnmanagedSourceServerModule::GetSourceServerData
Возвращает данные исходного сервера для модуля. Вызывающий объект должен освободить ресурсы с помощью `CoTaskMemFree`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a>Параметры  
 `pDataByteCount`  
 [out] Указатель на `ULONG32` , получающий размер в байтах, данные исходного сервера.  
  
 `ppData`  
 [out] Указатель на возвращенный `pDataByteCount` значение.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс ISymUnmanagedSourceServerModule](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
