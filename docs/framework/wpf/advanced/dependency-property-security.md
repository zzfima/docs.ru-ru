---
title: "Безопасность свойства зависимости"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wrappers [WPF], access
- wrappers [WPF], security
- dependency properties [WPF], security
- security [WPF], wrappers
- validation [WPF], dependency properties
- dependency properties [WPF], access
- security [WPF], dependency properties
ms.assetid: d10150ec-90c5-4571-8d35-84bafa2429a4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c8c1dc0ea45efe32e36b649d92111fff3d5f61a7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="dependency-property-security"></a>Безопасность свойства зависимости
Свойства зависимости, как правило, считаются открытыми. Суть системы свойств [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] такова, что дать гарантии безопасности о значении свойства зависимости невозможно.  
  
  
<a name="AccessSecurity"></a>   
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>Доступ к программам-оболочкам и свойствам зависимости и их безопасность  
 Как правило, свойства зависимости реализуются вместе со свойствами [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] программы-оболочки, которые упрощают получение или настройку свойства от экземпляра. Очень просто удобные методы, реализующие базовый, но оболочки <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> статические вызовы, которые будут использоваться при взаимодействии со свойствами зависимости. Другими словами, свойства предоставляются как свойства [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], поддерживаемые свойством зависимости, а не закрытым полем. Механизмы безопасности, применяемые к программам-оболочкам, не поддерживают параллели между поведением системы свойств и доступом базового свойства зависимости. Помещение требования безопасности для оболочки только предотвратит использование подходящего метода, но не будет препятствовать вызовы <xref:System.Windows.DependencyObject.GetValue%2A> или <xref:System.Windows.DependencyObject.SetValue%2A>. Аналогично: размещение защищенного или закрытого уровня доступа в программе-разработчике не обеспечивает эффективную защиту.  
  
 При написании собственных свойств зависимости следует объявлять оболочки и <xref:System.Windows.DependencyProperty> поле идентификатора как открытые элементы, чтобы вызывающие объекты не получали неправильные сведения о действительном уровне доступа этого свойства (из-за его хранилище, реализовано как свойство зависимостей).  
  
 Для настраиваемого свойства зависимости, можно зарегистрировать свойство как доступное только для чтения свойство зависимостей, и это обеспечивают эффективные способы предотвращает устанавливаемое любым пользователем, не содержит ссылку на свойство <xref:System.Windows.DependencyPropertyKey> для данного свойства. Дополнительные сведения см. в разделе [Свойства зависимостей "только для чтения"](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md).  
  
> [!NOTE]
>  Объявление <xref:System.Windows.DependencyProperty> закрытого поля идентификатора не запрещено и он может быть использован для уменьшения немедленного предоставления пространства имен настраиваемого класса, но такое свойство не считается «private», в том же смысле, как [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] в определениях языка, и уровень доступа причин, описанных в следующем разделе.  
  
<a name="PropertySystemExposure"></a>   
## <a name="property-system-exposure-of-dependency-properties"></a>Предоставление системы свойств свойствам зависимости  
 Он обычно не имеет смысла, и это ложная для объявления <xref:System.Windows.DependencyProperty> как любого уровня доступа, отличного от общего. Такая настройка уровня доступа просто лишит возможности получить ссылку на экземпляр из объявляющего класса. Однако существует несколько аспектов системы свойств, которые возвращают <xref:System.Windows.DependencyProperty> как средства для идентификации конкретного свойства, как оно существует в экземпляр класса или экземпляра производного класса, и этот идентификатор можно по-прежнему использовать в <xref:System.Windows.DependencyObject.SetValue%2A> даже вызвать Если исходный статический идентификатор объявлен как nonpublic. Кроме того <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> виртуальные методы получать данные из любого существующего свойства зависимостей, измененное значение. Кроме того <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> метод возвращает идентификаторы для любого свойства в экземплярах с локально заданное значение.  
  
### <a name="validation-and-security"></a>Проверка и безопасность  
 Применение требований <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> и ожидается ошибка проверки при ошибке запросу для предотвращения задаваемое свойство не является достаточно безопасным механизмом. Установите значение недействительности регламентирует <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> может подавляться вредоносными вызывающими объектами, если эти объекты функционируют в домене приложения.  
  
## <a name="see-also"></a>См. также  
 [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
