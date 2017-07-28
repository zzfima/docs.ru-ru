---
title: "Устранение рисков. Язык и региональные параметры и операции диспетчеризации в приложениях WPF | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 455c1452-8ce0-45ae-a092-21fb8edf1cac
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1aee32c5c50c4ff4309f93bff270e6c3b3c8f7cc
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="mitigation-culture-and-dispatcher-operations-in-wpf-apps"></a>Устранение рисков. Язык и региональные параметры и операции диспетчеризации в приложениях WPF
В приложениях, предназначенных для .NET Framework 4.6 или .NET Framework 4.6.1, изменения свойств <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>, внесенные в <xref:System.Windows.Threading.Dispatcher>, теряются при завершении соответствующей операции диспетчеризации. Аналогичным образом, изменения <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>, внесенные за пределами операции диспетчеризации, не будут учитываться при выполнении этой операции.  
  
 Это связано с некоторыми изменениями в <xref:System.Threading.ExecutionContext>, в результате которых <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> хранятся в контексте выполнения. Операции диспетчеризации WPF сохраняют контекст выполнения, который используется для запуска операции и восстановления предыдущего контекста при завершении операции. Поскольку <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> теперь являются частью этого контекста, внесенные в рамках операции диспетчеризации изменения не сохраняются вне этой операции.  
  
## <a name="impact"></a>Последствия  
 Проще говоря, изменения <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> не передаются между вызовами пользовательского интерфейса WPF и другим кодом в приложении WPF.  
  
## <a name="mitigation"></a>Уменьшение  
 Для приложений, затронутых этим изменением, есть два решения.  
  
-   Сохранять нужные значения <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> в отдельном поле и проверять во всех операциях <xref:System.Windows.Threading.Dispatcher> (включая обработчики событий вызова пользовательского интерфейса), правильно ли установлены значения <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>.  
  
-   Поскольку изменение в <xref:System.Threading.ExecutionContext> затрагивает только приложения WPF, предназначенные для .NET Framework 4.6 или .NET Framework 4.6.1, можно обойти это изменение, нацелив приложение на .NET Framework 4.5.2 или на любую версию выше .NET Framework 4.6.2, включительно.  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
