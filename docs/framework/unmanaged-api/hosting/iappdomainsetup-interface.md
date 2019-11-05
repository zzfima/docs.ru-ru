---
title: Интерфейс IAppDomainSetup
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
ms.openlocfilehash: 0fab64c31d4a73995c16d21767f4569f21c7df9a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126876"
---
# <a name="iappdomainsetup-interface"></a>Интерфейс IAppDomainSetup
Предоставляет свойства, позволяющие узлу настроить тип <xref:System.AppDomain?displayProperty=nameWithType> перед вызовом метода [ICorRuntimeHost:: CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) для его создания.  
  
## <a name="properties"></a>Свойства  
  
|свойство;|Описание|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|Возвращает или задает имя каталога, содержащего приложение.|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|Возвращает или задает имя приложения.|  
|<xref:System.AppDomainSetup.CachePath%2A>|Возвращает или задает имя области, относящейся к приложению, в котором файлы копируются при теневом копировании.|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|Возвращает или задает имя файла конфигурации для приложения.|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|Возвращает или задает имя каталога, в котором хранятся и обращаются динамически создаваемые файлы.|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|Возвращает или задает путь к файлу лицензии, связанному с этим доменом.|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|Возвращает или задает список каталогов в сочетании с каталогом <xref:System.AppDomainSetup.ApplicationBase%2A> для проверки закрытых сборок.|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|Возвращает или задает строковое значение, включающее или исключающее <xref:System.AppDomainSetup.ApplicationBase%2A> из пути поиска для приложения.|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|Возвращает или задает имена каталогов, содержащих сборки для теневого копирования.|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|Возвращает или задает строку, которая указывает, включено ли теневое копирование. Допустимые значения: "true" или "false".|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `IAppDomainSetup` соответствует управляемому интерфейсу <xref:System.IAppDomainSetup>, который реализуется типом <xref:System.AppDomainSetup>. Подробное описание его свойств см. в разделе <xref:System.IAppDomainSetup?displayProperty=nameWithType>.  
  
 `IAppDomainSetup` представляет сведения о привязке сборки, которые можно добавить в экземпляр <xref:System.AppDomain> перед его созданием. Например, узел может задать свойство <xref:System.AppDomainSetup.ApplicationBase%2A>, чтобы установить корневой каталог, который проверяется средой CLR для управляемых сборок.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
