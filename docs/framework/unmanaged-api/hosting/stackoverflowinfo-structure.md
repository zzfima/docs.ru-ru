---
title: Структура StackOverflowInfo
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: 1072026f92edbc646653c6dd74ec8e22d5b887e5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105911"
---
# <a name="stackoverflowinfo-structure"></a>Структура StackOverflowInfo
Хранит тип произошедшего переполнения и сведения об исключении, порождаемом из-за переполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`soType`|Значение перечисления [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) , указывающее тип переполнения.|  
|`pExceptionInfo`|Указатель на объект Win32 `EXCEPTION_POINTERS`, который содержит запись исключения с независимым от компьютера описанием исключения и записью контекста с зависящим от компьютера описанием контекста процессора на момент возникновения исключения.|  
  
## <a name="remarks"></a>Заметки  
 Объект `StackOverflowInfo` передается в метод [иактиононклревент:: oneven](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) для событий `Event_StackOverflow`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. idl  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
