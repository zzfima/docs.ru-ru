---
title: "Объекты DiffGram | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Объекты DiffGram
DiffGram \- это формат XML, определяющий текущую и первоначальную версию элементов данных.  Набор данных <xref:System.Data.DataSet> использует формат DiffGram для загрузки и хранения своего содержимого, а также для сериализации содержимого перед отправкой его по сетевому подключению.  Если набор <xref:System.Data.DataSet> записан в формате DiffGram, то он заполняет DiffGram всеми необходимыми данными, чтобы точно воссоздать содержимое \(но не схему\) набора данных <xref:System.Data.DataSet>, включая значения столбцов, как из **первоначальной**, так и из **текущей** версий строк, сведения об ошибках строк и порядке строк.  
  
 При отправке и получении набора данных <xref:System.Data.DataSet> из веб\-службы XML формат DiffGram используется неявно.  Кроме того, при загрузке содержимого <xref:System.Data.DataSet> из XML с помощью метода **ReadXml** или при записи содержимого <xref:System.Data.DataSet> в XML с помощью метода **WriteXml** можно указывать, что содержимое должно считываться или записываться в формате DiffGram.  Дополнительные сведения см. в разделах [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) и [Запись содержимого DataSet в виде XML\-данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Хотя формат DiffGram в основном используется платформой .NET Framework как формат сериализации для содержимого набора данных <xref:System.Data.DataSet>, его можно также применять для изменения данных в таблицах базы данных Microsoft SQL Server.  
  
 Diffgram формируется путем записи содержимого всех таблиц в элемент **\<diffgram\>**.  
  
### Создание Diffgram  
  
1.  Создайте список корневых таблиц \(таблиц, не имеющих родителей\).  
  
2.  Для каждой таблицы и ее потомков в списке запишите текущую версию всех строк в первом разделе Diffgram.  
  
3.  Для каждой таблицы в наборе данных <xref:System.Data.DataSet> запишите первоначальную версию всех строк, если она есть, в разделе **\<before\>** Diffgram.  
  
4.  Для строк, имеющих ошибки, запишите содержимое ошибок в разделе **\<errors\>** Diffgram.  
  
 Diffgram обрабатывается в последовательном порядке от начала XML\-файла до его конца.  
  
### Обработка Diffgram  
  
1.  Обработайте первый раздел Diffgram, содержащий текущую версию строк.  
  
2.  Обработайте второй раздел, или раздел **\<before\>**, содержащий первоначальную версию измененных или удаленных строк.  
  
    > [!NOTE]
    >  Если строка помечена как удаленная, то операция удаления может удалить потомков этой строки в зависимости от свойства `Cascade` текущего набора данных <xref:System.Data.DataSet>.  
  
3.  Обработайте раздел **\<errors\>**.  Установите сведения об ошибках для всех заданных строк и столбцов каждого элемента в этом разделе.  
  
> [!NOTE]
>  Если в Diffgram задан режим <xref:System.Data.XmlWriteMode>, то содержимое целевого набора <xref:System.Data.DataSet> и исходного набора <xref:System.Data.DataSet> могут различаться.  
  
## Формат DiffGram  
 Формат дельты содержит три раздела: текущие данные, исходные данные и раздел ошибок, как показано в следующем примере.  
  
```  
<?xml version="1.0"?>  
<diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  
   <DataInstance>  
   </DataInstance>  
  
  <diffgr:before>  
  </diffgr:before>  
  
  <diffgr:errors>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
 Формат DiffGram состоит из следующих блоков данных:  
  
 **\<**  ***DataInstance***  **\>**  
 Имя этого элемента, ***DataInstance***, используется в этом документе для примера.  Элемент ***DataInstance*** представляет набор данных <xref:System.Data.DataSet> или строку таблицы <xref:System.Data.DataTable>.  Вместо *DataInstance* элемент будет носить имя набора данных <xref:System.Data.DataSet> или таблицы <xref:System.Data.DataTable>.  Этот блок формата DiffGram содержит текущие данные, независимо от изменений в этих данных.  Измененный элемент или строка определяется заметкой **diffgr:hasChanges**.  
  
 **Блок \<diffgr:before\>**  
 Этот блок формата DiffGram содержит первоначальную версию строки.  Элементы в этом блоке сопоставляются с элементами блока ***DataInstance*** с помощью заметки **diffgr:id**.  
  
 **Блок \<diffgr:errors\>**  
 Этот блок формата DiffGram содержит сведения об ошибках конкретной строки в блоке ***DataInstance***.  Элементы в этом блоке сопоставляются с элементами блока ***DataInstance*** с помощью заметки **diffgr:id**.  
  
## Заметки DiffGram  
 В формате DiffGrams используется несколько заметок для связывания элементов из разных блоков DiffGram, представляющих разные версии строк или сведения об ошибках в <xref:System.Data.DataSet>.  
  
 В следующей таблице представлены заметки DiffGram, которые определяются в пространстве имен DiffGram **urn:schemas\-microsoft\-com:xml\-diffgram\-v1**.  
  
|Комментарий|Описание|  
|-----------------|--------------|  
|**id**|Используется для сопоставления элементов в блоках **\<diffgr:before\>** и **\<diffgr:errors\>** с элементами в блоке **\<** ***DataInstance*** **\>**.  Значения заметки **diffgr:id** имеют вид *\[ИмяТаблицы\]\[ИдентификаторСтроки\]*.  Например, `<Customers diffgr:id="Customers1">`.|  
|**parentId**|Определяет, какой элемент из блока **\<** ***DataInstance*** **\>** является родительским для текущего элемента.  Значения заметки **diffgr:parentId** имеют вид *\[ИмяТаблицы\]\[ИдентификаторСтроки\]*.  Например, `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Определяет строку в блоке **\<** ***DataInstance*** **\>** как измененную.  Заметка **hasChanges** может принимать одно из следующих значений.<br /><br /> **inserted**<br /> Определяет **добавленную** строку.<br /><br /> **modified**<br /> Определяет **измененную** строку, содержащую **первоначальную** версию строки в блоке **\<diffgr:before\>**.  Обратите внимание, что **удаленные** строки будут иметь **первоначальную** версию строки в блоке **diffgr:before**, но в блоке **\<** ***DataInstance*** **\>** элемент с заметкой будет отсутствовать.|  
|**hasErrors**|Определяет строку в блоке **\<** ***DataInstance*** **\>** с элементом **RowError**.  Элемент ошибки помещается в блок **\<diffgr:errors\>**.|  
|**Ошибка**|Содержит текст **RowError** для конкретного элемента в блоке **\<diffgr:errors\>**.|  
  
 Набор данных <xref:System.Data.DataSet> содержит дополнительные заметки при считывании или записи содержимого в формате DiffGram.  В следующей таблице представлены дополнительные заметки, которые определены в пространстве имен DiffGram **urn:schemas\-microsoft\-com:xml\-msdata**.  
  
|Комментарий|Описание|  
|-----------------|--------------|  
|**RowOrder**|Сохраняет порядок строк исходных данных и определяет индекс строки в конкретной таблице <xref:System.Data.DataTable>.|  
|**Hidden**|Определяет столбец, свойство которого **ColumnMapping** имеет значение **MappingType.Hidden**.  Этот атрибут записывается в формате **msdata:hidden** *\[ИмяСтолбца\]*\="*значение*".  Например, `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Обратите внимание, что скрытые столбцы записываются как атрибут DiffGram только если они содержат данные.  В противном случае они пропускаются.|  
  
## Образец DiffGram  
 Ниже показан пример формата DiffGram.  На нем показан результат обновления строки в таблице перед фиксацией изменений.  Строка с идентификатором пользователя «ALFKI» была изменена, но не обновлена.  В результате есть **текущая** строка с идентификатором **diffgr:id** «Customers1» в блоке **\<** ***DataInstance*** **\>** и **первоначальная** строка с идентификатором **diffgr:id** «Customers1» в блоке **\<diffgr:before\>**.  Строка с идентификатором пользователя «ANATR» содержит элемент ошибки **RowError**, поэтому к ней в качестве заметки добавляется значение `diffgr:hasErrors="true"`, а в блоке **\<diffgr:errors\>** будет связанный элемент.  
  
```  
<diffgr:diffgram xmlns:msdata="urn:schemas-microsoft-com:xml-msdata" xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
  <CustomerDataSet>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0" diffgr:hasChanges="modified">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>New Company</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers2" msdata:rowOrder="1" diffgram:hasErrors="true">  
      <CustomerID>ANATR</CustomerID>  
      <CompanyName>Ana Trujillo Emparedados y Helados</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers3" msdata:rowOrder="2">  
      <CustomerID>ANTON</CustomerID>  
      <CompanyName>Antonio Moreno Taquera</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers4" msdata:rowOrder="3">  
      <CustomerID>AROUT</CustomerID>  
      <CompanyName>Around the Horn</CompanyName>  
    </Customers>  
  </CustomerDataSet>  
  <diffgr:before>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>Alfreds Futterkiste</CompanyName>  
    </Customers>  
  </diffgr:before>  
  <diffgr:errors>  
    <Customers diffgr:id="Customers2" diffgr:Error="An optimistic concurrency violation has occurred for this row."/>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
## См. также  
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Запись содержимого DataSet в виде XML\-данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)