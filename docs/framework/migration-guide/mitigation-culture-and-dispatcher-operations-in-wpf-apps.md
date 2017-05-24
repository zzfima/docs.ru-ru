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
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-culture-and-dispatcher-operations-in-wpf-apps"></a>Устранение рисков. Язык и региональные параметры и операции диспетчеризации в приложениях WPF
В приложениях, предназначенных для .NET Framework 4.6 и .NET Framework 4.6.1, изменения свойств <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>, которые выполняются в рамках <xref:System.Windows.Threading.Dispatcher>, теряются в конце операции диспетчеризации. Аналогичным образом, изменения свойств <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>, внесенные вне операции диспетчеризации, могут не отображаться при выполнении этой операции.  
  
 Это происходит из-за изменения в <xref:System.Threading.ExecutionContext>, вследствие которого <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> хранятся в контексте выполнения. Операции диспетчеризации WPF сохраняют контекст выполнения, который используется для запуска операции и восстановления предыдущего контекста при завершении операции. Поскольку <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> теперь являются частью этого контекста, их изменения, выполненные в рамках операции диспетчера, не сохраняются за пределами операции.  
  
## <a name="impact"></a>Последствия  
 На практике это означает, что изменения свойств <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> могут не передаваться между обратными вызовами пользовательского интерфейса WPF и другим кодом в приложении WPF.  
  
## <a name="mitigation"></a>Уменьшение  
 Для приложений, затронутых этим изменением, есть два решения.  
  
-   Хранение нужного свойства <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> в поле и выполнение во всех текстах операций <xref:System.Windows.Threading.Dispatcher> (включая обработчики обратного вызова событий пользовательского интерфейса) проверки правильности заданного свойства <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>.  
  
-   Поскольку изменение в <xref:System.Threading.ExecutionContext> затрагивает только приложения WPF, предназначенные для .NET Framework 4.6 или .NET Framework 4.6.1, этого изменения можно избежать ориентированием на .NET Framework 4.5.2 или на версию .NET Framework от 4.6.2 и выше.  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
