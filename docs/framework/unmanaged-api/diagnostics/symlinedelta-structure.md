---
title: Структура SYMLINEDELTA
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 77cd8b7d791d11f6d40386f4747c60cd4832521a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="symlinedelta-structure"></a>Структура SYMLINEDELTA
Предоставляет сведения о методах, перемещенных в результате редактирования обработчика символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`mdMethod`|Токен метаданных метода.|  
|`delta`|Число строк, что метод был перемещен.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl  
  
## <a name="see-also"></a>См. также  
 [Структуры хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
