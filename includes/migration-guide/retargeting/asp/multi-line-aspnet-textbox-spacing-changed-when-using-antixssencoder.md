---
ms.openlocfilehash: e2bca42daebd25667ab2f312d5e59089b986503c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774449"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>Изменены интервалы многострочного текстового поля ASP.NET при использовании AntiXSSEncoder

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.0 между строками многострочного текстового поля при обратной передаче вставлялись дополнительные строки, если использовался <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>. В .NET Framework 4.5 эти дополнительные разрывы строк отсутствуют только в том случае, если веб-приложение предназначено для .NET Framework 4.5|
|Предложение|Имейте в виду, что в веб-приложениях 4.0, перенаправленных на .NET Framework 4.5, многострочные текстовые поля могут быть усовершенствованы, чтобы больше не вставлять дополнительные разрывы строк. Если это нежелательно, для приложения, выполняющегося в .NET Framework 4.5, можно сохранить старое поведение путем изменения версии платформы на .NET Framework 4.0.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Изменение целевой платформы|
