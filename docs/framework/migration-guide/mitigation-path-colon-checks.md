---
title: Устранение рисков. Проверки двоеточий в путях
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e41a51dcdf243091d3962278f1a59a85a2722894
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "66251131"
---
# <a name="mitigation-path-colon-checks"></a>Устранение рисков. Проверки двоеточий в путях
Начиная с приложений, ориентированных на .NET Framework 4.6.2, выполнен ряд изменений для поддержки ранее не поддерживаемых путей (с точки зрения и длины, и формата). В частности, усовершенствованы проверки правильности синтаксиса разделителя диска (двоеточия).  
  
## <a name="impact"></a>Последствия  
 Эти изменения блокируют некоторые пути URI, которые ранее поддерживались методами <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> и <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>.  
  
## <a name="mitigation"></a>Устранение рисков  
 Чтобы обойти проблему с ранее допустимым путем, который больше не поддерживается методами <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> и <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>, можно сделать следующее:  
  
- Вручную удалить схему из URL-адреса. Например, удалить `file://` из URL-адреса.  
  
- передать код URI в конструктор <xref:System.Uri> и получить значение свойства <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>;  
  
- отказаться от новой нормализации путей, установив для параметра `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> значение `true`.  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a>См. также

- [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
