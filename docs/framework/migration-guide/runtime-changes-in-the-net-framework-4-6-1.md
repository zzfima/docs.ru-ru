---
title: "Изменения среды выполнения в .NET Framework 4.6.1 | Документы Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6.1
- application compatibility
ms.assetid: 9d97421c-5fee-4523-98c9-a158e7e6a1ee
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b8c6ec4d0bad4a769fb4d19a98c9e8a4eda0db78
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-461"></a>Изменения среды выполнения в .NET Framework 4.6.1
В редких случаях изменения среды выполнения могут повлиять на существующие приложения, предназначенные для предыдущих версий .NET Framework, но выполняющиеся в более поздней версии среды выполнения .NET Framework. Они также включают различия в поведении между приложениями, которые выполняются в разных средах .NET Framework. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] включает изменения в следующих областях:  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Привязка WCF с режимом безопасности `TransportWithMessageCredential`|По умолчанию привязка WCF, которая использует режим безопасности `TransportWithMessageCredential`, не разрешает сообщения с неподписанным заголовком "to" ("кому") для асимметричных ключей безопасности. Начиная с приложений, работающих в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], можно опускать это требование и получать сообщения с неподписанными заголовками "to".|Это поведение, включаемое пользователем. Чтобы разрешить сообщения с неподписанными заголовками "to", добавьте следующий параметр конфигурации в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:<br /><br /> `<runtime>     <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />  </runtime>`<br /><br /> Поскольку это возможность, включаемая пользователем, она не должна влиять на поведение существующих приложений.|Пограничный случай|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>|Когда <xref:System.Windows.Controls.ItemsControl> отображает коллекцию с использованием виртуализации (<xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> = `true`) и прокрутки элементов (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>) и когда элемент управления прокручивается для отображения элемента, высота которого в пикселях отличается от высоты соседних элементов, <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> выполняет итерацию по всем элементам в коллекции.   Пользовательский интерфейс не отвечает на запросы в ходе этой итерации; если коллекция большая, это может восприниматься как зависание.<br /><br /> Такая итерация происходит и в других ситуациях, даже в выпусках, предшествующих [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Например, она происходит при прокрутке пикселей (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>) до обнаружения элемента с другой высотой в пикселях и при прокрутке элементов иерархических данных (например, в элементе управления <xref:System.Windows.Controls.TreeView> или в <xref:System.Windows.Controls.ItemsControl> с включенным группированием) до обнаружения элемента с другим числом дочерних элементов, чем у его соседей.<br /><br /> В случае прокрутки элементов и разной высоты в пикселях итерация была введена в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] для исправления ошибок в макете иерархических данных.  Итерация не требуется, если данные не структурированы (без иерархии), и в этом случае [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] не выполняет ее.|Если итерация выполняется в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], но не в более ранних выпусках, т. е. если <xref:System.Windows.Controls.ItemsControl> прокручивает поэлементно плоский список с элементами разной высоты в пикселях, то существует два решения.<br /><br /> Установка [.NET Framework 4.6.2](../../../docs/framework/install/guide-for-developers.md).<br /><br /> Установка [исправления HR 1605](https://support.microsoft.com/en-us/kb/3154529) для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].|Дополнительный номер|  
## <a name="see-also"></a>См. также  
 [Совместимость приложений в 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
