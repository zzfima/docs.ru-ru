---
title: "Изменения среды выполнения в .NET Framework 4.5.2 | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 94ac01ea-8b12-44d2-b12b-5220a5d14d87
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 247fbf574f13985fc941f252c0a6e7268194c079
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="runtime-changes-in-the-net-framework-452"></a>Изменения среды выполнения в .NET Framework 4.5.2
В редких случаях изменения среды выполнения могут повлиять на существующие приложения, предназначенные для предыдущих версий .NET Framework, но выполняющиеся в среде выполнения .NET Framework 4.5.2. Они включают изменения в следующих областях.  
  
-   [ASP.NET](#ASP_NET)  
  
-   [Entity Framework](#EF)  
  
<a name="ASP_NET"></a>   
## <a name="aspnet-runtime-changes"></a>Изменения среды выполнения ASP.NET  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Атрибут `enableViewStateMac` [элемента pages](http://msdn.microsoft.com/en-us/4123bb66-3fe4-4d62-b70e-33758656b458)|ASP.NET теперь не позволяет разработчикам указывать:<br /><br /> `<pages enableViewStateMac="false" />`<br /><br /> или<br /><br /> `<@Page EnableViewStateMac="false" %>`|Код проверки подлинности сообщения (MAC) состояния просмотра теперь принудительно применяется для всех запросов со встроенным состоянием просмотра. Затрагиваются только те приложения, в которых для свойства <xref:System.Web.UI.Page.EnableViewStateMac%2A> явно задано значение `false`.<br /><br /> Дополнительные сведения см. в статье [Устранение ошибок, связанных с состоянием вида кода проверки подлинности сообщения (MAC)](http://support.microsoft.com/kb/2915218).|Значительно|  
  
<a name="EF"></a>   
## <a name="entity-framework-runtime-changes"></a>Изменения среды выполнения Entity Framework  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Отношения через представление QueryView|Entity Framework больше не создает исключение <xref:System.StackOverflowException>, если приложение выполняет запрос, включающий представление QueryView со свойством навигации 0..1, которое пытается включить связанные объекты в запрос (например, вызывая метод `.Include(e=>e.RelatedNavProp)`).|Это изменение влияет только на код, использующий представления QueryView с отношениями 1-0..1 при выполнении запросов, вызывающих метод `.Include`. Эта функция повышает надежность и должна быть прозрачна почти для всех приложений. Тем не менее, если она вызывает непредвиденное поведение, ее можно отключить, добавив следующую запись в раздел `<appSettings>` файла конфигурации приложения:<br /><br /> `<add key="EntityFramework_SimplifyUserSpecifiedViews"  value="false" />`|Пограничный случай|  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-2.md)   
 [Совместимость приложений в 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Совместимость приложений в 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)
