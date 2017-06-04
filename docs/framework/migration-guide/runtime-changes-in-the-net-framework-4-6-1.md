---
title: "Изменения среды выполнения в .NET Framework 4.6.1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "изменения среды выполнения, платформа .NET Framework"
  - "изменения среды выполнения, платформа .NET Framework 4.6.1"
  - "совместимость приложений"
ms.assetid: 9d97421c-5fee-4523-98c9-a158e7e6a1ee
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# Изменения среды выполнения в .NET Framework 4.6.1
В редких случаях изменения среды выполнения могут повлиять на существующие приложения, предназначенные для предыдущих версий .NET Framework, но выполняющиеся в более поздней версии среды выполнения .NET Framework. Они также включают различия в поведении между приложениями, которые выполняются в разных средах .NET Framework. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] Включает изменения в следующих областях:  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Привязки WCF с `TransportWithMessageCredential` режима безопасности|По умолчанию WCF привязка, которая использует `TransportWithMessageCredential` режим безопасности не допускает сообщения с неподписанный «в «заголовок для асимметричным ключам. Начиная с приложениями, которые работают под [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], существует возможность опускать это требование и получать сообщения, которые не выполнили вход» «заголовки.|Это поведение, включаемое пользователем. Чтобы разрешить сообщения с, без подписи «на «заголовки, добавьте следующий параметр конфигурации для [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) раздел файла конфигурации приложения:<br /><br /> `<runtime>     <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />  </runtime>`<br /><br /> Поскольку это возможность, включаемая пользователем, она не должна влиять на поведение существующих приложений.|Пограничный случай|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>|Когда <xref:System.Windows.Controls.ItemsControl> отображает коллекцию с помощью виртуализации (<xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> = `true`) и прокрутки элемента (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>), и при прокрутке элемента управления, чтобы отобразить элемент высоту в пикселях которого отличается от своих соседей <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> перебор всех элементов в коллекции.   Пользовательский Интерфейс не отвечает на запросы в ходе этой итерации;  Если коллекция является большой, это может восприниматься как зависания.<br /><br /> Итерация в других случаях, даже в выпусках, предшествующих [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Например, происходит при прокрутке пикселей (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>) при обнаружении элемента с высоты другой точки, а также при прокрутке элемента иерархических данных (например, в <xref:System.Windows.Controls.TreeView> управления или <xref:System.Windows.Controls.ItemsControl> с группированием включен) при обнаружении элемента с другим числом подчиненных элементов от своих соседей.<br /><br /> В случае высота прокрутки элемента и различные точки итерации была введена в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] для исправления ошибок в макете иерархических данных.  Не требуется, если данные неструктурированного (без иерархии имеет) и [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] не делает этого в этом случае.|При итерации в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] , но не в более ранних выпусках--Если <xref:System.Windows.Controls.ItemsControl> элемент прокрутке плоский список с элементами другой пикселей высоты--существует два решения:<br /><br /> Установка [.NET Framework 4.6.2](../../../docs/framework/install/guide-for-developers.md).<br /><br /> Установка [исправление HR 1605](https://support.microsoft.com/en-us/kb/3154529) для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].|Дополнительный номер|  
  
## <a name="see-also"></a>См. также  
 [Совместимость приложений в 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)