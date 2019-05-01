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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 34d93c6956ff391e4d8726d8e45265c96947ad4c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986405"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a>Метод ISymUnmanagedReader::ReplaceSymbolStore
Заменяет имеющееся хранилище символов разностным хранилищем символов. Этот метод аналогичен методу [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) метода, за исключением того, что данная разность действует как полная замена, а не для обновления.  
  
> [!NOTE]
>  Вы должны указать только один из `filename` или `pIStream` параметров, не оба. Если `filename` указан, обновляется в хранилище символов с символами в этом файле. Если `pIStream` указан, хранилище будет обновлено с данными из <xref:System.Runtime.InteropServices.ComTypes.IStream>.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>Параметры  
 `filename`  
 [in] Имя файла, содержащего хранилище символов.  
  
 `pIStream`  
 [in] Файловый поток, используемый в качестве альтернативы для `filename` параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
