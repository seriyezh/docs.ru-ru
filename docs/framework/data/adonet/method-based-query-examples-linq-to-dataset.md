---
title: "Примеры запросов на основе методов (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d340775c-7f39-4087-a290-5cbec6cfa68e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1c34420d567e030eb681dbe90a4154e7b709daf7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="method-based-query-examples-linq-to-dataset"></a>Примеры запросов на основе методов (LINQ to DataSet)
В этом разделе приведены примеры программирования [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] с использованием синтаксиса запросов на основе методов, в которых используются стандартные операторы запросов. <xref:System.Data.DataSet> Используется в этих примерах заполняется с помощью `FillDataSet` метод, который указывается в [загрузка данных в наборе данных](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md). Дополнительные сведения см. в разделе [Общие сведения о стандартных операторах запроса](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Проекция](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-projection.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.Select%2A> и <xref:System.Linq.Enumerable.SelectMany%2A> для запроса к <xref:System.Data.DataSet>.  
  
 [Секционирование](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-partitioning-linq.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.Skip%2A> и <xref:System.Linq.Enumerable.Take%2A> для запроса <xref:System.Data.DataSet> и секционирования результатов.  
  
 [Упорядочение](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> и <xref:System.Linq.Enumerable.ThenByDescending%2A> для запроса к <xref:System.Data.DataSet> и упорядочения результатов.  
  
 [Операторы задания](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-set-operators.md)  
 В примерах этого раздела показано, как использовать операторы <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A> и <xref:System.Linq.Enumerable.Union%2A> для сравнения на основе значений наборов и рядов данных.  
  
 [Операторы преобразования](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-conversion-operators.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> и <xref:System.Linq.Enumerable.ToList%2A> для немедленного выполнения выражения запроса.  
  
 [Операторы элементов](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-element-operators.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.First%2A> и <xref:System.Linq.Enumerable.ElementAt%2A> для получения элементов <xref:System.Data.DataRow> из <xref:System.Data.DataSet>.  
  
 [Операторы статистических выражений](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-aggregate-operators.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> и <xref:System.Linq.Enumerable.Sum%2A> для запроса <xref:System.Data.DataSet> и статистической обработки данных.  
  
 [Join](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-join-linq-to-dataset.md)  
 Примеры в данном разделе демонстрируют, как использовать методы <xref:System.Linq.Enumerable.GroupJoin%2A> и <xref:System.Linq.Enumerable.Join%2A> для запроса к <xref:System.Data.DataSet>.  
  
## <a name="see-also"></a>См. также  
 [Примеры выражений запросов](../../../../docs/framework/data/adonet/query-expression-examples-linq-to-dataset.md)  
 [Связанные с определенными наборами данных примеры операторов](../../../../docs/framework/data/adonet/dataset-specific-operator-examples-linq-to-dataset.md)  
 [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
