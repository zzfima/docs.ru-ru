---
title: Метод ISymUnmanagedWriter::RemapToken
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec4a486b9dfb72c05a9e614fca22626dd84a83f7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468470"
---
# <a name="isymunmanagedwriterremaptoken-method"></a>Метод ISymUnmanagedWriter::RemapToken
Уведомляет модуль записи символов, что маркер метаданных был повторно сопоставлен при выдаче метаданных. Если модуль записи символов хранимая старый токен в хранилище символов, его необходимо либо обновить хранимые маркеры новое значение, либо сохранить сопоставление для соответствующего средства чтения символов для повторного сопоставления на этапе считывания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a>Параметры  
 `oldToken`  
 [in] Токен метаданных, который был переназначен.  
  
 `newToken`  
 [in] Новый маркер метаданных, к которому `oldToken` был переназначен.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
