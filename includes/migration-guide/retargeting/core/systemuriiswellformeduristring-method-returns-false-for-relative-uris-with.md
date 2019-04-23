---
ms.openlocfilehash: 734041f5921571cd11225a359e794526cbd8d0e1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774473"
---
### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a>Метод System.Uri.IsWellFormedUriString возвращает значение false для относительных URI с символом двоеточия в первом сегменте

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.5 <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> будет рассматривать относительные URI с <code>:</code> в первом сегменте как некорректные. Это отличается от поведения <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name> в .NET Framework 4.0. Изменение было внесено, чтобы обеспечить соответствие RFC3986.|
|Предложение|Это изменение (как и другие изменения URI) повлияет только на приложения, предназначенные для .NET Framework 4.5 (или более поздней версии). Чтобы сохранить старое поведение, необходимо нацелить приложение на .NET Framework 4.0. Кроме того, проверьте URI до вызова метода <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name>, ищущего символы <code>:</code>, которые можно удалить в целях проверки, если вы предпочитаете старое поведение.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType></li></ul>|
