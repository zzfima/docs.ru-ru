---
title: "Интерфейс ICLRRuntimeInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo
helpviewer_keywords: ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 287e5ede-b3a7-4ef8-a756-4fca3f285a82
topic_type: apiref
caps.latest.revision: "27"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 86861ae1742cf520d1a5251c70a112b090ec429e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfo-interface"></a>Интерфейс ICLRRuntimeInfo
Предоставляет методы, возвращающие сведения о конкретных общеязыковая среда выполнения (CLR), включая версию, каталог и состояние загрузки. Этот интерфейс также предоставляет функциональные возможности среды выполнения без инициализации среды выполнения. Он включает относительный среды выполнения [LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) метод, специфичная для модуля среды выполнения [GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) метод и интерфейсов предоставляемые средой выполнения с помощью [GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)метод.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Bindaslegacyv2runtime-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)|Привязывает эту среду выполнения для всех предыдущих версий среды CLR версии 2 решений политики активации.|  
|[Getdefaultstartupflags-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getdefaultstartupflags-method.md)|Получает флаги загрузки среды CLR и файл конфигурации главного узла.|  
|[GetInterface-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)|Загружает среду CLR в текущий процесс и возвращает среды выполнения указателей интерфейса, такие как [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) и [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md). Этот метод заменяет все `CorBindTo*` функции.|  
|[GetProcAddress-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)|Получает адрес указанной функции, которая была экспортирована из среды CLR, связанной с этим интерфейсом. Этот метод заменяет [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) метод.|  
|[Getruntimedirectory-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)|Получает каталог установки среды CLR, связанной с этим интерфейсом. Этот метод заменяет [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) метод.|  
|[Метод GetVersionString](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getversionstring-method.md)|Возвращает общий язык среды выполнения (CLR) сведения о версии данной [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейса. Этот метод заменяет [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md) и [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) методы.|  
|[IsLoadable-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloadable-method.md)|Указывает, возможна ли загрузка среды выполнения, связанных с этим интерфейсом в текущий процесс, принимая во внимание других сред выполнения, которые уже могли быть загружены в процесс.|  
|[IsLoaded-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloaded-method.md)|Указывает ли среда CLR, связанный с [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс загружается в процесс.|  
|[IsStarted-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isstarted-method.md)|Указывает, является ли среда CLR, связанный с [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс был запущен.|  
|[Loaderrorstring-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loaderrorstring-method.md)|Преобразовывает значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров. Этот метод заменяет [LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md) и [LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md) методы.|  
|[LoadLibrary-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)|Загружает библиотеку из каталога платформы среды CLR, представляемой [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейса. Этот метод заменяет [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) метод.|  
|[Setdefaultstartupflags-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md)|Задает флаги загрузки среды CLR и узла файла конфигурации.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
