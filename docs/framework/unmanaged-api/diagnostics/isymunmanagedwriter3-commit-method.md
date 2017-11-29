---
title: "Метод ISymUnmanagedWriter3::Commit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter3.Commit
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter3::Commit
helpviewer_keywords:
- Commit method, ISymUnmanagedWriter3 interface [.NET Framework debugging]
- ISymUnmanagedWriter3::Commit method [.NET Framework debugging]
ms.assetid: f6961922-46ec-4d2c-8369-85f880731f37
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3ff2baa8a5006e2a3a83ddbcf5ca79b78350794b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter3commit-method"></a>Метод ISymUnmanagedWriter3::Commit
Фиксирует изменения, записанных в поток.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Commit();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Isymunmanagedwriter3-интерфейс](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
