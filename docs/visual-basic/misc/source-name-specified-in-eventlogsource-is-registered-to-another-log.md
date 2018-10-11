---
title: Имя источника, указанное в EventLogSource, зарегистрировано в журнале, отличном от указанного в EventLogName
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: 03fcc41b0fbb84233aa037d7af17d168050a98b6
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086372"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a>Имя источника, указанное в EventLogSource, зарегистрировано в журнале, отличном от указанного в EventLogName
`EventLog` пытается сослаться на источник, который зарегистрирован в другом журнале. Для добавления записей в журнал событий необходимо задать свойство <xref:System.Diagnostics.EventLog.Source%2A> . Свойство <xref:System.Diagnostics.EventLog.Source%2A> регистрирует компонент в журнале событий в качестве допустимого источника записей. Один источник может быть связан только с одним журналом событий одновременно (и поэтому может добавлять записи только в него).  
  
 По умолчанию при попытке добавить запись в журнал без предварительной регистрации компонента в качестве разрешенного источника система автоматически регистрирует его в этом журнале, используя значение свойства <xref:System.Diagnostics.EventLog.Source%2A> в качестве строки источника.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь в том, что источник зарегистрирован в соответствующем журнале. Для этого используйте метод <xref:System.Diagnostics.EventLog.CreateEventSource%2A> или одну из его перегрузок, чтобы указать строку, однозначно идентифицирующую компонент в журнале событий.  
  
## <a name="see-also"></a>См. также  
 [Администрирование журнала событий](https://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)  
 [Ссылки на журнал событий](https://msdn.microsoft.com/library/4af0661c-6c96-49f4-961d-b26ed9bc3e87)  
 [Практическое: добавьте приложение в качестве источника записей журнала событий](https://msdn.microsoft.com/library/948ff920-a739-4e66-a191-ee951512d42c)  
 [Практическое: удалить источник событий](https://msdn.microsoft.com/library/bc66c900-4b8a-426a-b8e2-17031a20167e)
