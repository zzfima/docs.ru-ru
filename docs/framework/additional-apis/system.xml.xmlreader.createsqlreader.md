---
title: Метод XmlReader.CreateSqlReader (System.Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 7bd2ef5158516acede47f73f9937d06159bc16c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155743"
---
# <a name="xmlreadercreatesqlreader-method"></a>Метод XmlReader.CreateSqlReader

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

## <a name="returns"></a>Результаты

<xref:System.Xml.XmlReader>  
Объект, используемый для чтения данных XML в потоке.

## <a name="remarks"></a>Remarks

> [!WARNING]
> Метод `XmlReader.CreateSqlReader` является внутренним и не предназначен для использования непосредственно в коде.
>
> Корпорация Майкрософт ни при каких обстоятельствах не поддерживает использование этого метода в производственном приложении.

## <a name="requirements"></a>Требования

**Пространство имен:**<xref:System.Xml>

**Сборка:** System.Xml.dll

**Рамочные версии .NET:** Доступно с 2.0.
