---
title: Использование средств разработки WCF
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 1ffa3be4a6b8976ab978ea995e8b2c1faaacf0ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144642"
---
# <a name="using-the-wcf-development-tools"></a>Использование средств разработки WCF
В этом разделе описываются средства разработки Visual Studio, которые могут помочь в разработке служб WCF.  
  
 Можно использовать шаблоны Visual Studio как основу для быстрого создания собственной службы, а затем использовать для отладки и тестирования службы WCF Service Auto Host и тестового клиента WCF. Оба этих инструмента обеспечивают быстрый и удобный цикл отладки и тестирования и исключают необходимость фиксации модели размещения на ранней стадии.  
  
## <a name="the-wcf-developer-tools"></a>Инструменты разработчика WCF  
 [Шаблоны WCF в Visual Studio](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 Предопределенных шаблонов проектов и элементов Visual Studio в Visual Studio можно использовать для быстрого создания служб WCF и окружающих приложений.  
  
 [Узел службы WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 WCF Service Auto Host (WcfSvcHost.exe) позволяет запустить отладчик Visual Studio (F5) для автоматического размещения и проверки службы, реализованный. Затем можно проверить службу, используя клиент тестирования WCF (wcfTestClient.exe) или своего собственного клиента для поиска и устранения потенциальных ошибок.  
  
 [Тестовый клиент WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 Тестовый клиент WCF (WcfTestClient.exe) это средство графического интерфейса пользователя, которое позволяет вводить параметры произвольных типов, отправлять их в службу и представление, которое отправляет ответ службы. Он предоставляет удобный способ тестирования в сочетании с WCF Service Auto Host служб.  
  
 [Формирование классов типов данных из XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 Данные XML, сохраненные в буфере обмена, можно вставить в кодовую страницу. Классы, определенные в данных, будут преобразованы в типы кода.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Использование инструментов без прав администратора  
 Чтобы разрешить пользователям без прав администратора для разработки служб WCF, создается список ACL (список управления доступом) для пространства имен "http://+:8731/Design_Time_Addresses" во время установки Visual Studio. Список управления доступом определяется пользовательским интерфейсом, который включает всех пользователей, выполнивших вход в систему. Администраторы могут добавлять или удалять пользователей из этого списка ACL или открыть дополнительные порты. Этот список ACL позволяет шаблонам WCF или WF отправлять и получать данные в их конфигурации по умолчанию. Он также позволяет пользователям использовать WCF Service Auto Host (wcfSvcHost.exe) без предоставления им прав администратора.  
  
 Можно изменить доступ используя средство Netsh.exe в [!INCLUDE[wv](../../../includes/wv-md.md)] под учетной записью администратора. Ниже приведен пример использования средства Netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Дополнительные сведения о Netsh.exe см. в разделе [способы использования средства Netsh.exe и переключателей командной строки](https://go.microsoft.com/fwlink/?LinkId=97877).  
  
## <a name="see-also"></a>См. также

- [Шаблоны WCF в Visual Studio](../../../docs/framework/wcf/wcf-vs-templates.md)
- [Узел службы WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
- [Тестовый клиент WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
