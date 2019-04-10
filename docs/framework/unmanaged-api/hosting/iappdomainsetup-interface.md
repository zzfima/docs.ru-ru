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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbde873481aea9de94862117a99079301965f33c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220075"
---
# <a name="iappdomainsetup-interface"></a>Интерфейс IAppDomainSetup
Предоставляет свойства, позволяющие узла настроить <xref:System.AppDomain?displayProperty=nameWithType> типа до вызова метода [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) метод для его создания.  
  
## <a name="properties"></a>Свойства  
  
|Свойство|Описание|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|Возвращает или задает имя каталога, содержащего приложение.|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|Возвращает или задает имя приложения.|  
|<xref:System.AppDomainSetup.CachePath%2A>|Возвращает или задает имя области, определенной для приложения расположение файлов, которые теневого копирования.|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|Получает или задает имя файла конфигурации для приложения.|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|Получает или задает имя каталога, где хранятся и доступны динамически создаваемые файлы.|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|Возвращает или задает путь к файлу лицензии, связанный с этим доменом.|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|Возвращает или задает список каталогов, в сочетании с <xref:System.AppDomainSetup.ApplicationBase%2A> directory для проверки наличия закрытых сборок.|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|Возвращает или задает строковое значение, которое включает или исключает <xref:System.AppDomainSetup.ApplicationBase%2A> из пути поиска для приложения.|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|Возвращает или задает имена каталогов, содержащих сборки, подлежащие теневому копированию.|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|Получает или задает строку, указывающую, определить, включено ли теневое копирование. Допустимые значения: «true» или «false».|  
  
## <a name="remarks"></a>Примечания  
 `IAppDomainSetup` Соответствующий интерфейс в управляемый <xref:System.IAppDomainSetup> интерфейс, который <xref:System.AppDomainSetup> введите реализует. См. в разделе <xref:System.IAppDomainSetup?displayProperty=nameWithType> подробное описание его свойств.  
  
 `IAppDomainSetup` Представляет сведения о привязке сборок, которые могут добавляться к <xref:System.AppDomain> экземпляра до его создания. Например, узел может присвоить параметру <xref:System.AppDomainSetup.ApplicationBase%2A> свойство, чтобы установить корневой каталог, который среда CLR (CLR) проверяет наличие управляемых сборок.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
