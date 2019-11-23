---
title: Программа командной строки настройки модели служб COM+ (ComSvcConfig.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM+ integration
- WCF, COM+ integration
ms.assetid: 7717c6c2-85fc-418b-a8ed-bad8e61cec5c
ms.openlocfilehash: 13368dfa7ca9d7981ac146b87e83f77077eaf537
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320725"
---
# <a name="com-service-model-configuration-tool-comsvcconfigexe"></a>Программа командной строки настройки модели служб COM+ (ComSvcConfig.exe)
Программа командной строки для настройки модели служб COM+ (ComSvcConfig.exe) позволяет настраивать интерфейсы COM+, которые нужно предоставить как веб-службы.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
ComSvcConfig.exe /install | /uninstall | /list [/application:<ApplicationID | ApplicationName>] [/contract:<ClassID | ProgID | *,InterfaceID | InterfaceName | *>] [/hosting:<complus | was>] [/webSite:<WebsiteName>] [/webDirectory:<WebDirectoryName>] [/mex] [/id] [/nologo] [/verbose] [/help] [/partial]  
```  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Для использования ComSvcConfig.exe на компьютере под управлением ОС Windows Vista требуются права администратора.  
  
 Это средство можно найти в следующей папке:  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\  
  
 Дополнительные сведения о программе ComSvcConfig. exe см. в разделе [как использовать средство настройки модели службы COM+](./feature-details/how-to-use-the-com-service-model-configuration-tool.md).  
  
 В следующей таблице представлены режимы, которые могут использоваться с ComSvcConfig.exe.  
  
|Параметр|Описание|  
|------------|-----------------|  
|`install`|Устанавливает конфигурацию для интерфейса COM+ для интеграции Service Model.<br /><br /> Краткая форма: `/i`.|  
|`uninstall`|Удаляет конфигурацию для интерфейса COM+ из интеграции Service Model.<br /><br /> Краткая форма: `/u`.|  
|`list`|Отображает сведения о приложениях и компонентах COM+, которые имеют интерфейсы, настроенные для интеграции Service Model.<br /><br /> Краткая форма: `/l`.|  
  
 В следующей таблице представлены флаги, которые могут использоваться с ComSvcConfig.exe.  
  
|Параметр|Описание|  
|------------|-----------------|  
|`/application:` \<*applicationId* &#124; *applicationName*\>|Позволяет указать приложение COM+ для настройки.<br /><br /> Краткая форма: `/a`.|  
|`/contract:` \< &#124; *идентификатор ProgID* &#124; \*,*InterfaceID* &#124; *interfacename* &#124; \*\>|Позволяет указать компонент и интерфейс COM+, которые будут настроены в качестве контракта для службы.<br /><br /> Краткая форма: `/c`.<br /><br /> Хотя подстановочный знак (\*) можно использовать при указании имен компонентов и интерфейсов, рекомендуется не использовать его, так как вы можете предоставлять интерфейсы, которые не планировались.|  
|`/hosting:` \<*ComPlus* &#124; *\>*|Позволяет указать необходимость использования режима размещения COM+ или режима размещения на веб-сервере.<br /><br /> Краткая форма: `/h`.<br /><br /> Для использования режима размещения COM+ требуется явная активация приложения COM+. Использование режима размещения на веб-сервере позволяет автоматически активировать приложение COM+ при необходимости. Если приложение COM+ является библиотечным приложением, оно выполняется в процессе IIS. Если приложение COM+ является серверным приложением, оно выполняется в процессе Dllhost.exe.|  
|`/webSite:` \<*имя_веб*\>|Позволяет указать веб-сайт для размещения при использовании режима размещения на веб-сервере (см. флаг `/hosting`).<br /><br /> Краткая форма: `/w`.<br /><br /> Если веб-сайт не указан, используется веб-сайт по умолчанию.|  
|`/webDirectory:` \<*вебдиректоринаме*\>|Позволяет указать виртуальный каталог для размещения при использовании режима размещения на веб-сервере (см. флаг `/hosting`).<br /><br /> Краткая форма: `/d`.|  
|`/mex`|Добавляет конечную точку службы обмена метаданными в конфигурацию службы по умолчанию для поддержки клиентов, которым требуется извлечь определение контракта из службы.<br /><br /> Краткая форма: `/x`.|  
|`/id`|Отображает информацию о приложении, компоненте и интерфейсе в виде идентификаторов.<br /><br /> Краткая форма: `/k`.|  
|`/nologo`|Подавляет отображение логотипа ComSvcConfig.exe.<br /><br /> Краткая форма: `/n`.|  
|`/verbose`|Выводит все предупреждения или информационный текст в дополнение к любым обнаруженным ошибкам.<br /><br /> Краткая форма: `/v`.|  
|`/help`|Отображает сообщение об использовании.<br /><br /> Краткая форма: `/?`.|  
|`/partial`|Создает конфигурацию службы, если указанный интерфейс включает одну или несколько сигнатур метода, которые могут быть предоставлены для использования. Во время инициализации службы совместимые методы отображаются как операции над контрактом службы, а несовместимые методы игнорируются и исключаются из контракта службы.<br /><br /> Если данный флаг отсутствует, средство не создает конфигурацию службы, когда указанный интерфейс включает один или несколько несовместимых методов.|  
  
## <a name="examples"></a>Примеры  
  
### <a name="description"></a>Описание  
 В следующем примере с помощью режима размещения COM+ выполняется добавление интерфейса `IFinances` компонента `ItemOrders.IFinancial` (из приложения COM+ OnlineStore) в набор интерфейсов, предоставляемых как веб-службы. В дополнение к любым обнаруженным ошибкам выводятся все предупреждения.  
  
### <a name="code"></a>Код  
  
```console  
ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
```  
  
### <a name="description"></a>Описание  
 В следующем примере с помощью режима размещения на веб-сервере выполняется добавление интерфейса `IStockLevels` компонента `ItemInventory.Warehouse` (из приложения COM+ OnlineWarehouse) в набор интерфейсов, предоставляемых как веб-службы. Веб-служба размещается в виртуальном каталоге OnlineWarehouse в IIS.  
  
### <a name="code"></a>Код  
  
```console  
ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse  
```  
  
### <a name="description"></a>Описание  
 В следующем примере выполняется удаление интерфейса `IFinances` компонента `ItemOrders.Financial` (из приложения COM+ OnlineStore) из набора интерфейсов, предоставляемых как веб-службы.  
  
### <a name="code"></a>Код  
  
```console  
ComSvcConfig.exe /uninstall /application:OnlineStore /interface:ItemOrders.Financial,IFinances /hosting:complus  
```  
  
### <a name="description"></a>Описание  
 В следующем примере выводится список предоставляемых в данный момент интерфейсов, размещенных в COM+, а также соответствующий адрес и сведения о привязке для приложения COM+ OnlineStore на локальном компьютере.  
  
### <a name="code"></a>Код  
  
```console  
ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
```  
  
## <a name="see-also"></a>См. также:

- [Практическое руководство. Использование программы командной строки настройки модели служб COM+](./feature-details/how-to-use-the-com-service-model-configuration-tool.md)
