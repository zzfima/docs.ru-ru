---
title: Использование средств разработки WCF
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 82bb7e225492bcdba4d2e611de405a09571355c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183083"
---
# <a name="using-the-wcf-development-tools"></a>Использование средств разработки WCF
В этом разделе описаны инструменты разработки Visual Studio, которые могут помочь вам в разработке WCFservice.  
  
 Вы можете использовать шаблоны Visual Studio в качестве основы для быстрого создания собственного сервиса, а затем использовать WCF Service Auto Host и WCF Test Client для отладки и тестирования сервиса. Оба этих инструмента обеспечивают быстрый и удобный цикл отладки и тестирования и исключают необходимость фиксации модели размещения на ранней стадии.  

 > [!NOTE]
 > Начиная с Visual Studio 2017, инструменты разработки WCF не устанавливаются по умолчанию. Для использования этих функций необходимо убедиться, что компонент Windows Communication Foundation выбран в установке Visual Studio.
  
## <a name="the-wcf-developer-tools"></a>Инструменты разработчика WCF  
 [Шаблоны WCF в Visual Studio](wcf-vs-templates.md)  
  
 Вы можете использовать предопределенные visual Studio проект и шаблоны элементов в Visual Studio для быстрого создания wCF-сервисов и окружающих приложений.  
  
 [Узел службы WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)  
  
 Автохост WCF Service Auto Host (WcfSvcHost.exe) позволяет запустить Visual Studio-отладчик (F5) для автоматического размещения и тестирования услуги, которая была реализована. Затем вы можете протестировать сервис с помощью испытательного клиента WCF (wcfTestClient.exe) или собственного клиента, чтобы найти и исправить любые потенциальные ошибки.  
  
 [Тестовый клиент WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)  
  
 WCF Test Client (WcfTestClient.exe) — это инструмент GUI, позволяющий ввести параметры произвольных типов, представить этот вход в службу и просмотреть ответ службы. Он обеспечивает бесшовный опыт тестирования службы в сочетании с WCF Сервис Автохост.  
  
 [Формирование классов типов данных из XML](generating-data-type-classes-from-xml.md)  
  
 Данные XML, сохраненные в буфере обмена, можно вставить в кодовую страницу. Классы, определенные в данных, будут преобразованы в типы кода.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Использование инструментов без прав администратора  
 Для того, чтобы пользователи, не имеющие привилегий администратора, могли разрабатывать сервисы WCF, во время установки Visual Studio создается ACL (Список управления доступом) для пространства имен «http://+:8731/Design_Time_Addressesво время установки Visual Studio. Список управления доступом определяется пользовательским интерфейсом, который включает всех пользователей, выполнивших вход в систему. Администраторы могут добавлять или удалять пользователей из этого списка ACL или открыть дополнительные порты. Этот список ACL позволяет шаблонам WCF или WF отправлять и получать данные в их конфигурации по умолчанию. Он также позволяет пользователям использовать WCF Сервис Авто Хост (wcfSvcHost.exe) без предоставления им привилегий администратора.  
  
 Вы можете изменить доступ с помощью инструмента Netsh.exe в Windows Vista под учетной записью повышенной администратора. Ниже приведен пример использования средства Netsh.exe.  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Для получения дополнительной информации о Netsh.exe, [см.](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10))  
  
## <a name="see-also"></a>См. также раздел

- [Шаблоны WCF в Visual Studio](wcf-vs-templates.md)
- [Узел службы WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [Тестовый клиент WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
