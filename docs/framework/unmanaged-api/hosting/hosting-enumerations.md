---
title: "Размещение перечислений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged enumerations [.NET Framework], hosting
- enumerations [.NET Framework hosting]
- hosting enumerations [.NET Framework]
ms.assetid: e09131eb-1f7d-4f52-ae42-7393e9b62ef6
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f415b4f3062a83f97d2bf186981289cf16e555a4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-enumerations"></a>Размещение перечислений
В этом разделе описываются неуправляемые перечисления, которые использует API размещения.  
  
## <a name="in-this-section"></a>Содержание  
 [Clsid_resolution_flags-перечисление](../../../../docs/framework/unmanaged-api/hosting/clsid-resolution-flags-enumeration.md)  
 Содержит значения, указывающие способ разрешения общеязыковой среды выполнения (CLR) `CLSID`.  
  
 [COR_GC_STAT_TYPES-перечисление](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)  
 Указывает статистику, записываемую для сборки мусора.  
  
 [Cor_gc_thread_stats_types-перечисление](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-types-enumeration.md)  
 Указывает статистику сборки мусора для потока.  
  
 [EApiCategories-перечисление](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 Описывает категории возможностей, которые узел может блокировать при выполнении в частично доверенном коде.  
  
 [Ebindpolicylevels-перечисление](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md)  
 Предоставляет флаги, указывающие уровень, на котором следует применять или изменять политику сборки.  
  
 [Eclrassemblyidentityflags-перечисление](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md)  
 Указывает тип удостоверения сборки.  
  
 [EClrEvent-перечисление](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 Описывает события среды CLR, для которых узел может регистрировать обратные вызовы.  
  
 [EClrFailure-перечисление](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 Описывает набор сбоев, для которых узел может задать действия политики.  
  
 [EClrOperation-перечисление](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 Описывает набор операций, для которых узел может применять действия политики.  
  
 [Eclrunhandledexception-перечисление](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)  
 Описывает доступные параметры для управления исключениями, которые обрабатываются в пользовательском коде.  
  
 [Econtexttype-перечисление](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 Описывает контекст безопасности текущего потока.  
  
 [Ecustomdumpflavor-перечисление](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 Содержит значения, указывающие, какие элементы будут включены в пользовательское подмножество кучи дампа при сообщении об ошибках.  
  
 [Ecustomdumpitemkind-перечисление](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 Зарезервировано для будущего расширения [CustomDumpItem-структура](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) структуры.  
  
 [Ehostapplicationpolicy-перечисление](../../../../docs/framework/unmanaged-api/hosting/ehostapplicationpolicy-enumeration.md)  
 Указывает, как изменить [ihostassemblymanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md) объект интерфейса. Это перечисление является устаревшим.  
  
 [Ehostbindingpolicymodifyflags-перечисление](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md)  
 Предоставляет узлу возможность определить тип перенаправления, которое должна выполнять среда CLR при применении изменений политики из исходной сборки на целевую сборку.  
  
 [Einitializenewdomainflags-перечисление](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)  
 Ведущее приложение может предоставлять среде выполнения сведения об инициализации домена приложения.  
  
 [Ememoryavailable-перечисление](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md)  
 Содержит значения, указывающие объем свободной физической памяти на компьютере.  
  
 [Ememorycriticallevel-перечисление](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)  
 Содержит значения, указывающие влияние сбоя в случае, когда был запрошен определенного выделения памяти, но не может быть удовлетворен.  
  
 [EPolicyAction-перечисление](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 Описывает действия политики, основное приложение может задать для операций, описанных [прерываниях](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) и сбоев, описанных [EClrFailure-перечисление](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).  
  
 [Esymbolreadingpolicy-перечисление](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md)  
 Содержит значения, задать политику для чтения файлов базы данных (PDB).  
  
 [Etasktype-перечисление](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md)  
 Содержит значения, указывающие тип задачи, представленной [ICLRTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) или [IHostTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) интерфейс.  
  
 [Перечисление HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md)  
 Содержит значения, указывающие тип узла, которое запускает приложение.  
  
 [Malloc_type-перечисление](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md)  
 Содержит значения, указывающие характеристики выделяемой памяти.  
  
 [METAHOST_CONFIG_FLAGS-перечисление](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md)  
 Описывает возможные флаги, возвращаемых в `pdwConfigFlags` параметр [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) метод.  
  
 [METAHOST_POLICY_FLAGS-перечисление](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)  
 Предоставляет политики привязки, которые являются общими для большинства сред выполнения.  
  
 [Runtime_info_flags-перечисление](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)  
 Содержит значения, указывающие, какие сведения о среде CLR должны возвращаться.  
  
 [Stackoverflowtype-перечисление](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md)  
 Содержит значения, которые указывают на основную причину события переполнения стека.  
  
 [STARTUP_FLAGS-перечисление](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)  
 Содержит значения, которые указывают поведение среды CLR при запуске.  
  
 [Validatorflags-перечисление](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)  
 Содержит значения, указывающие тип проверки, которые должны быть выполнены при обращении к [метод Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md).  
  
 [Wait_option-перечисление](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)  
 Указывает действие, которое должен предпринять узел, если операцию, запрошенную блоки со средой CLR.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Размещение компонентных классов](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
  
 [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
