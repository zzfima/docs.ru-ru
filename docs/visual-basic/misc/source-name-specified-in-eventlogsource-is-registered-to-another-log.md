---
title: "Имя источника, указанное в EventLogSource, зарегистрировано в журнале, отличном от указанного в EventLogName"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c190caa7634760c2e4dc4a2bb7a9a09f532eb0ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a>Имя источника, указанное в EventLogSource, зарегистрировано в журнале, отличном от указанного в EventLogName
`EventLog` пытается сослаться на источник, который зарегистрирован в другом журнале. Для добавления записей в журнал событий необходимо задать свойство <xref:System.Diagnostics.EventLog.Source%2A> . Свойство <xref:System.Diagnostics.EventLog.Source%2A> регистрирует компонент в журнале событий в качестве допустимого источника записей. Один источник может быть связан только с одним журналом событий одновременно (и поэтому может добавлять записи только в него).  
  
 По умолчанию при попытке добавить запись в журнал без предварительной регистрации компонента в качестве разрешенного источника система автоматически регистрирует его в этом журнале, используя значение свойства <xref:System.Diagnostics.EventLog.Source%2A> в качестве строки источника.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь в том, что источник зарегистрирован в соответствующем журнале. Для этого используйте метод <xref:System.Diagnostics.EventLog.CreateEventSource%2A> или одну из его перегрузок, чтобы указать строку, однозначно идентифицирующую компонент в журнале событий.  
  
## <a name="see-also"></a>См. также  
 [Администрирование журналов событий](http://msdn.microsoft.com/en-us/35f53238-bdd2-417b-acd8-2fd9f7397f18)  
 [Ссылки на журнал событий](http://msdn.microsoft.com/en-us/4af0661c-6c96-49f4-961d-b26ed9bc3e87)  
 [Способ: добавить приложение в качестве источника записей журнала событий](http://msdn.microsoft.com/en-us/948ff920-a739-4e66-a191-ee951512d42c)  
 [Как: удалить источник событий](http://msdn.microsoft.com/en-us/bc66c900-4b8a-426a-b8e2-17031a20167e)
