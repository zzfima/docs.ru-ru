---
title: "Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3bae0e2dfb56883a674b282acd385ba45a25bebb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a>Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
Задает смещение для обработчика catch, созданный компилятором, являющийся оболочкой для асинхронного метода на промежуточном Языке.  
  
 Смещение на промежуточном Языке созданный catch используется отладчиком для обработки catch, как если бы не написанный пользователем, несмотря на то, что она может возникать в метода кода пользователя. В частности, он используется в ответ на **CatchHandlerFound** события исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает `HRESULT`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
