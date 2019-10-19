---
title: Метод XmlReader. Креатесклреадер (System. XML)
author: mairaw
ms.author: mairaw
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 302be4eff32d2c96a1571d291e0b289e77694db8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582784"
---
# <a name="xmlreadercreatesqlreader-method"></a>XmlReader. Креатесклреадер, метод

Создает новый экземпляр <xref:System.Xml.XmlReader>, используя заданный поток, параметры и контекстную информацию для анализа.

```csharp
internal static XmlReader CreateSqlReader(Stream input, 
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a>Параметры

- `input` <xref:System.IO.Stream>  
  Поток, содержащий XML-данные.

- `settings` <xref:System.Xml.XmlReaderSettings>  
  Параметры нового экземпляра <xref:System.Xml.XmlReader>. Это значение может быть равно `null`.

- `inputContext` <xref:System.Xml.XmlParserContext>  
  Для синтаксического анализа фрагмента XML необходимы контекстные сведения. Это значение может быть равно `null`.

## <a name="returns"></a>Returns

<xref:System.Xml.XmlReader>  
Объект, используемый для чтения данных XML в потоке.

## <a name="remarks"></a>Заметки

> [!WARNING]
> Метод `XmlReader.CreateSqlReader` является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Xml>

**Сборка:** System. XML. dll

**.NET Framework версии:** Доступно с 2,0.
