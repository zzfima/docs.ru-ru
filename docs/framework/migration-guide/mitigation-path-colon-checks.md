---
title: "Устранение рисков. Проверки двоеточий в путях"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8eb6864213aa4420f7a4373b9abbf173880f035f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-path-colon-checks"></a>Устранение рисков. Проверки двоеточий в путях
Начиная с приложений, ориентированных на [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], выполнен ряд изменений для поддержки ранее не поддерживаемых путей (с точки зрения и длины, и формата). В частности, усовершенствованы проверки правильности синтаксиса разделителя диска (двоеточия).  
  
## <a name="impact"></a>Последствия  
 Эти изменения блокируют некоторые пути URI, которые ранее поддерживались методами <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> и <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName>.  
  
## <a name="mitigation"></a>Уменьшение  
 Чтобы обойти проблему с ранее допустимым путем, который больше не поддерживается методами <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> и <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName>, можно сделать следующее:  
  
-   Вручную удалить схему из URL-адреса. Например, удалить `file://` из URL-адреса.  
  
-   передать код URI в конструктор <xref:System.Uri> и получить значение свойства <xref:System.Uri.LocalPath%2A?displayProperty=fullName>;  
  
-   отказаться от новой нормализации путей, установив для параметра `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> значение `true`.  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

