---
title: Интерфейс ICorDebugAppDomain
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
ms.openlocfilehash: 9abcb765357a0f305ae5acae77a4a13b07a003a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134687"
---
# <a name="icordebugappdomain-interface"></a>Интерфейс ICorDebugAppDomain

Предоставляет методы для отладки доменов приложения. Этот интерфейс является подклассом ICorDebugController.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Attach](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|Присоединяет отладчик к домену приложения.|  
|[Метод EnumerateAssemblies](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Возвращает перечислитель для сборок в домене приложения.|  
|[Метод EnumerateBreakpoints](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|Возвращает перечислитель для всех активных точек останова в домене приложения.|  
|[Метод EnumerateSteppers](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|Возвращает перечислитель для всех активных шагов в домене приложения.|  
|[Метод GetId](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|Возвращает уникальный идентификатор домена приложения.|  
|[Метод GetModuleFromMetaDataInterface](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|Возвращает объект ICorDebugModule с заданным интерфейсом метаданных.|  
|[Метод GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|Возвращает имя домена приложения.|  
|[Метод GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|Возвращает указатель интерфейса на домен приложения среды CLR.|  
|[Метод GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|Возвращает процесс, содержащий домен приложения.|  
|[Метод IsAttached](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|Определяет, присоединен ли отладчик к домену приложения.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
