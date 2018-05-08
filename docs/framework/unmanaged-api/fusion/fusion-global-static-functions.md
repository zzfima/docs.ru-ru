---
title: Глобальные статические функции Fusion
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86cb59c0935c193a9865d5ace5fe11c96226d9e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fusion-global-static-functions"></a>Глобальные статические функции Fusion
В этом разделе описываются неуправляемые глобальные статические функции, используемые API Fusion.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Функция ClearDownloadCache](../../../../docs/framework/unmanaged-api/fusion/cleardownloadcache-function.md)  
 Очищает глобальный кэш сборок загруженных сборок.  
  
 [Функция CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 Сравнивает два идентификатора сборки, чтобы определить, эквивалентны ли они.  
  
 [Функция CreateApplicationContext](../../../../docs/framework/unmanaged-api/fusion/createapplicationcontext-function.md)  
 Только для внутреннего использования. (Эта функция поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).  
  
 [Функция CreateAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/createassemblycache-function.md)  
 Возвращает указатель на новый [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) экземпляр, представляющий глобальный кэш сборок.  
  
 [Функция CreateAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/createassemblyenum-function.md)  
 Возвращает указатель на [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) экземпляр, который представляет список объектов, существующих в заданной сборке.  
  
 [Функция CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 Возвращает указатель на [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) экземпляр, представляющий уникальный идентификатор сборки с указанным именем.  
  
 [Функция CreateHistoryReader](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 Создает средство чтения журнала для указанного файла.  
  
 [Функция CreateInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/createinstallreferenceenum-function.md)  
 Возвращает указатель на [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) экземпляр, представляющий список ссылок приложения для указанной сборки.  
  
 [Функция GetAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/getappidauthority-function.md)  
 Возвращает указатель на [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) экземпляр, который управляет ключами для идентификаторов и ссылок приложения.  
  
 [Функция GetAssemblyIdentityFromFile](../../../../docs/framework/unmanaged-api/fusion/getassemblyidentityfromfile-function.md)  
 Возвращает указатель на `IUnknown` объект с указанным `IID` сборки по указанному пути.  
  
 [Функция GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 Возвращает путь к кэшированной сборки, используя указанные флаги.  
  
 [Функция GetHistoryFileDirectory](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 Возвращает путь к каталогу журнала приложения.  
  
 [Функция GetIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/getidentityauthority-function.md)  
 Возвращает указатель на [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) экземпляр, который управляет ключи для объектов кода.  
  
 [Функция IsFrameworkAssembly](../../../../docs/framework/unmanaged-api/fusion/isframeworkassembly-function.md)  
 Возвращает значение, указывающее, является ли указанная сборка управляемой.  
  
 [Функция NukeDownloadedCache](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 Удаляет кэше загрузки среды выполнения.  
  
 [Функция PreBindAssemblyEx](../../../../docs/framework/unmanaged-api/fusion/prebindassemblyex-function.md)  
 Возвращает после применения политики отображаемое имя сборки.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
  
 [Перечисления Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [Структуры Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
  
 [Глобальный кэш сборок](../../../../docs/framework/app-domains/gac.md)
