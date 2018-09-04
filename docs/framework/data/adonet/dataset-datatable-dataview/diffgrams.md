---
title: DiffGrams
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: fd452efff2a26b66c06a7762b215df140047286d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43558331"
---
# <a name="diffgrams"></a>DiffGrams
DiffGram - это формат XML, определяющий текущую и первоначальную версию элементов данных. Набор данных <xref:System.Data.DataSet> использует формат DiffGram для загрузки и хранения своего содержимого, а также для сериализации содержимого перед отправкой его по сетевому подключению. При <xref:System.Data.DataSet> записывается в формате DiffGram, он заполняет DiffGram с всю необходимую информацию, чтобы точно воссоздать содержимое, но не схему из <xref:System.Data.DataSet>, включая значения столбцов из обоих **исходный** и **текущей** версии строк, сведения об ошибках строк и порядке строк.  
  
 При отправке и получении набора данных <xref:System.Data.DataSet> из веб-службы XML формат DiffGram используется неявно. Кроме того при загрузке содержимого <xref:System.Data.DataSet> из XML с помощью **ReadXml** метод, или при записи содержимого <xref:System.Data.DataSet> в XML с помощью **WriteXml** метод, можно указать что содержимое быть прочитана или записана в формате DiffGram. Дополнительные сведения см. в разделе [загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) и [запись содержимого набора данных как XML-данные](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Хотя формат DiffGram в основном используется платформой .NET Framework как формат сериализации для содержимого набора данных <xref:System.Data.DataSet>, его можно также применять для изменения данных в таблицах базы данных Microsoft SQL Server.  
  
 Diffgram формируется путем записи содержимого всех таблиц в  **\<diffgram >** элемент.  
  
### <a name="to-generate-a-diffgram"></a>Создание Diffgram  
  
1.  Создайте список корневых таблиц (таблиц, не имеющих родителей).  
  
2.  Для каждой таблицы и ее потомков в списке запишите текущую версию всех строк в первом разделе Diffgram.  
  
3.  Для каждой таблицы в <xref:System.Data.DataSet>, запишите первоначальную версию всех строк, если все в  **\<перед >** раздел Diffgram.  
  
4.  Для строк, имеющих ошибки, запишите содержимое ошибок в  **\<ошибки >** раздел Diffgram.  
  
 Diffgram обрабатывается в последовательном порядке от начала XML-файла до его конца.  
  
### <a name="to-process-a-diffgram"></a>Обработка Diffgram  
  
1.  Обработайте первый раздел Diffgram, содержащий текущую версию строк.  
  
2.  Обработайте второй или  **\<перед >** раздел, содержащий первоначальную версию измененных или удаленных строк.  
  
    > [!NOTE]
    >  Если строка помечена как удаленная, то операция удаления может удалить потомков этой строки в зависимости от свойства `Cascade` текущего набора данных <xref:System.Data.DataSet>.  
  
3.  Процесс  **\<ошибки >** раздел. Установите сведения об ошибках для всех заданных строк и столбцов каждого элемента в этом разделе.  
  
> [!NOTE]
>  Если в Diffgram задан режим <xref:System.Data.XmlWriteMode>, то содержимое целевого набора <xref:System.Data.DataSet> и исходного набора <xref:System.Data.DataSet> могут различаться.  
  
## <a name="diffgram-format"></a>Формат DiffGram  
 Формат дельты содержит три раздела: текущие данные, исходные данные и раздел ошибок, как показано в следующем примере.  
  
```xml  
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
  
 **\<**  ***DataInstance***  **>**  
 Имя этого элемента ***DataInstance***, используется для в этом документе. Объект ***DataInstance*** элемент представляет <xref:System.Data.DataSet> или строку таблицы <xref:System.Data.DataTable>. Вместо *DataInstance*, элемент будет носить имя <xref:System.Data.DataSet> или <xref:System.Data.DataTable>. Этот блок формата DiffGram содержит текущие данные, независимо от изменений в этих данных. Элемент, или строки, которые были изменены идентифицируется с помощью **diffgr: HasChanges** заметки.  
  
 **\<diffgr:before>**  
 Этот блок формата DiffGram содержит первоначальную версию строки. Элементы в этом блоке сопоставляются с элементами в ***DataInstance*** запретить, используя **diffgr: ID** заметки.  
  
 **\<diffgr: Errors >**  
 Этот блок формата DiffGram содержит сведения об ошибке для конкретной строки в ***DataInstance*** блока. Элементы в этом блоке сопоставляются с элементами в ***DataInstance*** запретить, используя **diffgr: ID** заметки.  
  
## <a name="diffgram-annotations"></a>Заметки DiffGram  
 В формате DiffGrams используется несколько заметок для связывания элементов из разных блоков DiffGram, представляющих разные версии строк или сведения об ошибках в <xref:System.Data.DataSet>.  
  
 В следующей таблице описаны заметки DiffGram, которые определены в пространстве имен DiffGram **urn: schemas-microsoft-com: XML-diffgram-v1**.  
  
|Комментарий|Описание|  
|----------------|-----------------|  
|**id**|Используется для сопоставления элементов в  **\<diffgr: перед >** и  **\<diffgr: Errors >** блоков к элементам в **\<** ***DataInstance*** **>** блока. Значения с **diffgr: ID** заметки представлены в виде *[Имя_таблицы] [Идентификаторстроки]*. Например, `<Customers diffgr:id="Customers1">`.|  
|**parentId**|Определяет, какой элемент из **\<** ***DataInstance*** **>** блок является родительским элементом текущего элемента. Значения с **diffgr: parentID** заметки представлены в виде *[Имя_таблицы] [Идентификаторстроки]*. Например, `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Определяет строку в **\<** ***DataInstance*** **>** блокировать как измененное. **HasChanges** заметка может иметь одно из следующих двух значений:<br /><br /> **inserted**<br /> Идентифицирует **Added** строки.<br /><br /> **Изменения**<br /> Идентифицирует **Modified** строки, содержащей **исходного** версию строки в  **\<diffgr: перед >** блока. Обратите внимание, что **Deleted** строки будут иметь **исходного** версию строки в  **\<diffgr: перед >** блок, но не с заметками элемент в будет**\<** ***DataInstance*** **>** блока.|  
|**hasErrors**|Определяет строку в **\<** ***DataInstance*** **>** блоке с **RowError**. Элемент ошибки помещается в  **\<diffgr: Errors >** блока.|  
|**Ошибка**|Содержит текст **RowError** для конкретного элемента в  **\<diffgr: Errors >** блока.|  
  
 Набор данных <xref:System.Data.DataSet> содержит дополнительные заметки при считывании или записи содержимого в формате DiffGram. В следующей таблице описаны эти дополнительные заметки, которые определены в пространстве имен **urn: schemas-microsoft-com: XML-msdata**.  
  
|Комментарий|Описание|  
|----------------|-----------------|  
|**RowOrder**|Сохраняет порядок строк исходных данных и определяет индекс строки в конкретной таблице <xref:System.Data.DataTable>.|  
|**Скрытые**|Определяет столбец как имеющий **ColumnMapping** свойство значение **MappingType.Hidden**. Этот атрибут записывается в формате **msdata: Скрытый** *[Имя_столбца]*=»*значение*«. Например, `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Обратите внимание, что скрытые столбцы записываются как атрибут DiffGram только если они содержат данные. В противном случае они пропускаются.|  
  
## <a name="sample-diffgram"></a>Образец DiffGram  
 Ниже показан пример формата DiffGram. На нем показан результат обновления строки в таблице перед фиксацией изменений. Строка с идентификатором пользователя «ALFKI» была изменена, но не обновлена. Таким образом, нет **текущей** строке со **diffgr: ID** «Customers1» в **\<** ***DataInstance*** **>** блока и **исходного** строке со **diffgr: ID** «Customers1» в  **\<diffgr: перед >** блок. Включает строку со значением CustomerID «ANATR» **RowError**, поэтому к ней с помощью `diffgr:hasErrors="true"` и нет связанного элемента в  **\<diffgr: Errors >** блока.  
  
```xml  
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
  
## <a name="see-also"></a>См. также  
 [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Запись содержимого DataSet как данных XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
