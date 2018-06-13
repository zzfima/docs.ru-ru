---
title: Практическое руководство. Миграция кода клиента веб-службы ASP.NET на платформу Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
ms.openlocfilehash: cb60f9cb2e8f35ee703b049eae9e3d99c1ec7d49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491134"
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a>Практическое руководство. Миграция кода клиента веб-службы ASP.NET на платформу Windows Communication Foundation
Следующая процедура описывает общих действия, которые необходимо соблюдать порядок переноса кода клиента веб-службы ASP.NET в WCF.  
  
## <a name="procedure"></a>Процедура  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a>Миграция кода клиента службы ASP.NET в WCF  
  
1.  Убедитесь в наличии комплексного набора тестов для клиента.  
  
2.  С помощью Visual Studio 2005 обновите клиентское приложение до .NET 2.0. Выполните набор тестов.  
  
3.  Удалите код клиента ASP.NET из клиентского проекта. Этот код находится в модулях, сформированных с помощью программы WSDL.exe.  
  
4.  Создание кода клиента WCF с помощью [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Добавьте этот код в клиентский проект и объедините полученную конфигурацию с существующим файлом конфигурации клиента.  
  
5.  Скомпилируйте приложение. Исправьте ошибки компиляции, заменив ссылки на старые клиентские типы ASP.NET со ссылками на новые типы клиента WCF.  
  
6.  Выполните набор тестов.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Миграция кода веб-службы ASP.NET на платформу Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
