---
title: "Устранение рисков. Проверки двоеточий в путях | Документация Майкрософт"
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
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b5e2426fc81c8fd38994a4124cf71af8ec445bfb
ms.contentlocale: ru-ru
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-path-colon-checks"></a>Устранение рисков. Проверки двоеточий в путях
Начиная с приложений, ориентированных на [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], выполнен ряд изменений для поддержки ранее не поддерживаемых путей (с точки зрения и длины, и формата). В частности, усовершенствованы проверки правильности синтаксиса разделителя диска (двоеточия).  
  
## <a name="impact"></a>Последствия  
 Эти изменения блокируют некоторые пути URI, которые ранее поддерживались методами <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> и <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName>.  
  
## <a name="mitigation"></a>Уменьшение  
 Чтобы обойти проблему ранее приемлемого пути, который больше не поддерживается методами <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> и <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName>, можно сделать следующее:  
  
-   Вручную удалить схему из URL-адреса. Например, удалить `file://` из URL-адреса.  
  
-   Перейти в URI <xref:System.Uri> и извлечь значение свойства <xref:System.Uri.LocalPath%2A?displayProperty=fullName>.  
  
-   Отказаться от новой нормализации путей, установив для переключателя `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> значение `true`.  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

