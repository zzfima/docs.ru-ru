---
title: Метод ISymUnmanagedReader::ReplaceSymbolStore
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
ms.openlocfilehash: 60c3537a80c39f758f46e6f2f0a5f2bcd27350b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445737"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a>Метод ISymUnmanagedReader::ReplaceSymbolStore
Заменяет имеющееся хранилище символов разностным хранилищем символов. Этот метод аналогичен методу [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) , за исключением того, что данная Дельта действует как полная замена, а не как обновление.  
  
> [!NOTE]
> Необходимо указать только один из параметров `filename` или `pIStream`, но не оба. Если указан `filename`, хранилище символов будет обновлено символами из этого файла. Если указано `pIStream`, хранилище будет обновлено данными из <xref:System.Runtime.InteropServices.ComTypes.IStream>.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>Параметры  
 `filename`  
 окне Имя файла, содержащего хранилище символов.  
  
 `pIStream`  
 окне Файловый поток, используемый в качестве альтернативы параметру `filename`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
