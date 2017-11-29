---
title: "Метод ISymUnmanagedReader::ReplaceSymbolStore"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.ReplaceSymbolStore
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09bcad4898cf4d3310a96164bdc82006e185006f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a>Метод ISymUnmanagedReader::ReplaceSymbolStore
Заменяет имеющееся хранилище символов разностным хранилищем символов. Этот метод аналогичен [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) метода, за исключением того, что данная разность используется полная замена, а не для обновления.  
  
> [!NOTE]
>  Необходимо указать только одно из `filename` или `pIStream` параметров, не оба. Если `filename` указан, обновляется в хранилище символов с символами в этом файле. Если `pIStream` указан, хранилище будет обновлено с данными из <xref:System.Runtime.InteropServices.ComTypes.IStream>.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a>Параметры  
 `filename`  
 [in] Имя файла, содержащего хранилище символов.  
  
 `pIStream`  
 [in] Файловый поток, используемый в качестве альтернативы для `filename` параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [ISymUnmanagedReader-интерфейс](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
