---
title: Интерфейс1 ICorDebugAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9588ac26c698a8369f1ae4be89af7440a2dd1de4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546310"
---
# <a name="icordebugappdomain-interface1"></a>Интерфейс1 ICorDebugAppDomain
Предоставляет методы для отладки доменов приложения. Этот интерфейс является подклассом ICorDebugController.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод Attach](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|Присоединяет отладчик к домену приложения.|  
|[Метод EnumerateAssemblies](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Получает перечислитель для сборок в домене приложения.|  
|[Метод EnumerateBreakpoints](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|Возвращает перечислитель для всех активных точек останова в домене приложения.|  
|[Метод EnumerateSteppers](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|Возвращает перечислитель для всех активных средств организации пошагового режима в домене приложения.|  
|[Метод GetId](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|Получает уникальный идентификатор домена приложения.|  
|[Метод GetModuleFromMetaDataInterface](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|Получает объект ICorDebugModule с интерфейсом указанных метаданных.|  
|[Метод GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|Возвращает имя домена приложения.|  
|[Метод GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|Получает указатель интерфейса на домен приложения среды выполнения (CLR).|  
|[Метод GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|Получает процесс, содержащий домен приложения.|  
|[Метод IsAttached](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|Определяет, добавлен ли отладчик в домен приложения.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
