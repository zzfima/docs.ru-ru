---
title: "Коллекции схемы ODBC"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 889e84db39af1257d709ef049e18d4397ea700d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="aa9d2-102">Коллекции схемы ODBC</span><span class="sxs-lookup"><span data-stu-id="aa9d2-102">ODBC Schema Collections</span></span>
<span data-ttu-id="aa9d2-103">В данном разделе рассматривается поддержка коллекций схем для драйверов ODBC для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="aa9d2-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="aa9d2-104">Драйвер ODBC для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="aa9d2-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="aa9d2-105">Драйвер ODBC для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем.</span><span class="sxs-lookup"><span data-stu-id="aa9d2-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="aa9d2-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="aa9d2-106">Tables</span></span>  
  
-   <span data-ttu-id="aa9d2-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="aa9d2-107">Indexes</span></span>  
  
-   <span data-ttu-id="aa9d2-108">Столбцы</span><span class="sxs-lookup"><span data-stu-id="aa9d2-108">Columns</span></span>  
  
-   <span data-ttu-id="aa9d2-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="aa9d2-109">Procedures</span></span>  
  
-   <span data-ttu-id="aa9d2-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="aa9d2-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="aa9d2-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="aa9d2-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="aa9d2-112">Представления</span><span class="sxs-lookup"><span data-stu-id="aa9d2-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="aa9d2-113">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="aa9d2-113">Tables and Views</span></span>  
  
|<span data-ttu-id="aa9d2-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-114">ColumnName</span></span>|<span data-ttu-id="aa9d2-115">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="aa9d2-116">TABLE_CAT</span></span>|<span data-ttu-id="aa9d2-117">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-117">String</span></span>|  
|<span data-ttu-id="aa9d2-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="aa9d2-118">TABLE_SCHEM</span></span>|<span data-ttu-id="aa9d2-119">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-119">String</span></span>|  
|<span data-ttu-id="aa9d2-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-120">TABLE_NAME</span></span>|<span data-ttu-id="aa9d2-121">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-121">String</span></span>|  
|<span data-ttu-id="aa9d2-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-122">TABLE_TYPE</span></span>|<span data-ttu-id="aa9d2-123">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-123">String</span></span>|  
|<span data-ttu-id="aa9d2-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-124">REMARKS</span></span>|<span data-ttu-id="aa9d2-125">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="aa9d2-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="aa9d2-126">Indexes</span></span>  
  
|<span data-ttu-id="aa9d2-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-127">ColumnName</span></span>|<span data-ttu-id="aa9d2-128">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="aa9d2-129">TABLE_CAT</span></span>|<span data-ttu-id="aa9d2-130">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-130">String</span></span>|  
|<span data-ttu-id="aa9d2-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="aa9d2-131">TABLE_SCHEM</span></span>|<span data-ttu-id="aa9d2-132">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-132">String</span></span>|  
|<span data-ttu-id="aa9d2-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-133">TABLE_NAME</span></span>|<span data-ttu-id="aa9d2-134">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-134">String</span></span>|  
|<span data-ttu-id="aa9d2-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-135">NON_UNIQUE</span></span>|<span data-ttu-id="aa9d2-136">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-136">Int16</span></span>|  
|<span data-ttu-id="aa9d2-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="aa9d2-138">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-138">String</span></span>|  
|<span data-ttu-id="aa9d2-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-139">INDEX_NAME</span></span>|<span data-ttu-id="aa9d2-140">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-140">String</span></span>|  
|<span data-ttu-id="aa9d2-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-141">TYPE</span></span>|<span data-ttu-id="aa9d2-142">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-142">Int16</span></span>|  
|<span data-ttu-id="aa9d2-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="aa9d2-144">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-144">Int16</span></span>|  
|<span data-ttu-id="aa9d2-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-145">COLUMN_NAME</span></span>|<span data-ttu-id="aa9d2-146">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-146">String</span></span>|  
|<span data-ttu-id="aa9d2-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="aa9d2-147">ASC_OR_DESC</span></span>|<span data-ttu-id="aa9d2-148">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-148">String</span></span>|  
|<span data-ttu-id="aa9d2-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="aa9d2-149">CARDINATLITY</span></span>|<span data-ttu-id="aa9d2-150">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-150">Int32</span></span>|  
|<span data-ttu-id="aa9d2-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="aa9d2-151">PAGES</span></span>|<span data-ttu-id="aa9d2-152">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-152">Int32</span></span>|  
|<span data-ttu-id="aa9d2-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-153">FILTER_CONDITION</span></span>|<span data-ttu-id="aa9d2-154">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-154">String</span></span>|  
|<span data-ttu-id="aa9d2-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="aa9d2-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="aa9d2-156">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-156">String</span></span>|  
|<span data-ttu-id="aa9d2-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-158">Byte</span><span class="sxs-lookup"><span data-stu-id="aa9d2-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="aa9d2-159">Столбцы</span><span class="sxs-lookup"><span data-stu-id="aa9d2-159">Columns</span></span>  
  
|<span data-ttu-id="aa9d2-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-160">ColumnName</span></span>|<span data-ttu-id="aa9d2-161">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="aa9d2-162">TABLE_CAT</span></span>|<span data-ttu-id="aa9d2-163">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-163">String</span></span>|  
|<span data-ttu-id="aa9d2-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="aa9d2-164">TABLE_SCHEM</span></span>|<span data-ttu-id="aa9d2-165">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-165">String</span></span>|  
|<span data-ttu-id="aa9d2-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-166">TABLE_NAME</span></span>|<span data-ttu-id="aa9d2-167">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-167">String</span></span>|  
|<span data-ttu-id="aa9d2-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-168">COLUMN_NAME</span></span>|<span data-ttu-id="aa9d2-169">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-169">String</span></span>|  
|<span data-ttu-id="aa9d2-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-170">DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-171">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-171">Int16</span></span>|  
|<span data-ttu-id="aa9d2-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-172">TYPE_NAME</span></span>|<span data-ttu-id="aa9d2-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-173">String</span></span>|  
|<span data-ttu-id="aa9d2-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-174">COLUMN_SIZE</span></span>|<span data-ttu-id="aa9d2-175">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-175">Int32</span></span>|  
|<span data-ttu-id="aa9d2-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="aa9d2-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="aa9d2-177">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-177">Int32</span></span>|  
|<span data-ttu-id="aa9d2-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="aa9d2-179">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-179">Int16</span></span>|  
|<span data-ttu-id="aa9d2-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="aa9d2-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="aa9d2-181">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-181">Int16</span></span>|  
|<span data-ttu-id="aa9d2-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-182">NULLABLE</span></span>|<span data-ttu-id="aa9d2-183">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-183">Int16</span></span>|  
|<span data-ttu-id="aa9d2-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-184">REMARKS</span></span>|<span data-ttu-id="aa9d2-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-185">String</span></span>|  
|<span data-ttu-id="aa9d2-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="aa9d2-186">COLUMN_DEF</span></span>|<span data-ttu-id="aa9d2-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-187">String</span></span>|  
|<span data-ttu-id="aa9d2-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-189">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-189">Int16</span></span>|  
|<span data-ttu-id="aa9d2-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="aa9d2-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="aa9d2-191">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-191">Int16</span></span>|  
|<span data-ttu-id="aa9d2-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="aa9d2-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="aa9d2-193">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-193">Int32</span></span>|  
|<span data-ttu-id="aa9d2-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="aa9d2-195">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-195">Int32</span></span>|  
|<span data-ttu-id="aa9d2-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-196">IS_NULLABLE</span></span>|<span data-ttu-id="aa9d2-197">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-197">String</span></span>|  
|<span data-ttu-id="aa9d2-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="aa9d2-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="aa9d2-199">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-199">String</span></span>|  
|<span data-ttu-id="aa9d2-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="aa9d2-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="aa9d2-201">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-201">String</span></span>|  
|<span data-ttu-id="aa9d2-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-203">Byte</span><span class="sxs-lookup"><span data-stu-id="aa9d2-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="aa9d2-204">Процедуры</span><span class="sxs-lookup"><span data-stu-id="aa9d2-204">Procedures</span></span>  
  
|<span data-ttu-id="aa9d2-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-205">ColumnName</span></span>|<span data-ttu-id="aa9d2-206">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="aa9d2-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="aa9d2-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-208">String</span></span>|  
|<span data-ttu-id="aa9d2-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="aa9d2-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="aa9d2-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-210">String</span></span>|  
|<span data-ttu-id="aa9d2-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="aa9d2-212">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-212">String</span></span>|  
|<span data-ttu-id="aa9d2-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="aa9d2-214">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-214">Int32</span></span>|  
|<span data-ttu-id="aa9d2-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="aa9d2-216">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-216">Int32</span></span>|  
|<span data-ttu-id="aa9d2-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="aa9d2-218">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-218">Int32</span></span>|  
|<span data-ttu-id="aa9d2-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-219">REMARKS</span></span>|<span data-ttu-id="aa9d2-220">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-220">String</span></span>|  
|<span data-ttu-id="aa9d2-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="aa9d2-222">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="aa9d2-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="aa9d2-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="aa9d2-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-224">ColumnName</span></span>|<span data-ttu-id="aa9d2-225">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="aa9d2-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="aa9d2-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-227">String</span></span>|  
|<span data-ttu-id="aa9d2-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="aa9d2-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="aa9d2-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-229">String</span></span>|  
|<span data-ttu-id="aa9d2-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="aa9d2-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-231">String</span></span>|  
|<span data-ttu-id="aa9d2-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-232">COLUMN_NAME</span></span>|<span data-ttu-id="aa9d2-233">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-233">String</span></span>|  
|<span data-ttu-id="aa9d2-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-234">COLUMN_TYPE</span></span>|<span data-ttu-id="aa9d2-235">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-235">Int16</span></span>|  
|<span data-ttu-id="aa9d2-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-236">DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-237">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-237">Int16</span></span>|  
|<span data-ttu-id="aa9d2-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-238">TYPE_NAME</span></span>|<span data-ttu-id="aa9d2-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-239">String</span></span>|  
|<span data-ttu-id="aa9d2-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-240">COLUMN_SIZE</span></span>|<span data-ttu-id="aa9d2-241">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-241">Int32</span></span>|  
|<span data-ttu-id="aa9d2-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="aa9d2-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="aa9d2-243">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-243">Int32</span></span>|  
|<span data-ttu-id="aa9d2-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="aa9d2-245">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-245">Int16</span></span>|  
|<span data-ttu-id="aa9d2-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="aa9d2-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="aa9d2-247">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-247">Int16</span></span>|  
|<span data-ttu-id="aa9d2-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-248">NULLABLE</span></span>|<span data-ttu-id="aa9d2-249">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-249">Int16</span></span>|  
|<span data-ttu-id="aa9d2-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-250">REMARKS</span></span>|<span data-ttu-id="aa9d2-251">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-251">String</span></span>|  
|<span data-ttu-id="aa9d2-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="aa9d2-252">COLUMN_DEF</span></span>|<span data-ttu-id="aa9d2-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-253">String</span></span>|  
|<span data-ttu-id="aa9d2-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-255">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-255">Int16</span></span>|  
|<span data-ttu-id="aa9d2-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="aa9d2-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="aa9d2-257">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-257">Int16</span></span>|  
|<span data-ttu-id="aa9d2-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="aa9d2-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="aa9d2-259">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-259">Int32</span></span>|  
|<span data-ttu-id="aa9d2-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="aa9d2-261">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-261">Int32</span></span>|  
|<span data-ttu-id="aa9d2-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-262">IS_NULLABLE</span></span>|<span data-ttu-id="aa9d2-263">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-263">String</span></span>|  
|<span data-ttu-id="aa9d2-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="aa9d2-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="aa9d2-265">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-265">String</span></span>|  
|<span data-ttu-id="aa9d2-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="aa9d2-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="aa9d2-267">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-267">String</span></span>|  
|<span data-ttu-id="aa9d2-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-269">Byte</span><span class="sxs-lookup"><span data-stu-id="aa9d2-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="aa9d2-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="aa9d2-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="aa9d2-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-271">ColumnName</span></span>|<span data-ttu-id="aa9d2-272">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="aa9d2-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="aa9d2-274">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-274">String</span></span>|  
|<span data-ttu-id="aa9d2-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="aa9d2-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="aa9d2-276">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-276">String</span></span>|  
|<span data-ttu-id="aa9d2-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="aa9d2-278">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-278">String</span></span>|  
|<span data-ttu-id="aa9d2-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-279">COLUMN_NAME</span></span>|<span data-ttu-id="aa9d2-280">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-280">String</span></span>|  
|<span data-ttu-id="aa9d2-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-281">COLUMN_TYPE</span></span>|<span data-ttu-id="aa9d2-282">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-282">Int16</span></span>|  
|<span data-ttu-id="aa9d2-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-283">DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-284">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-284">Int16</span></span>|  
|<span data-ttu-id="aa9d2-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-285">TYPE_NAME</span></span>|<span data-ttu-id="aa9d2-286">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-286">String</span></span>|  
|<span data-ttu-id="aa9d2-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-287">COLUMN_SIZE</span></span>|<span data-ttu-id="aa9d2-288">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-288">Int32</span></span>|  
|<span data-ttu-id="aa9d2-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="aa9d2-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="aa9d2-290">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-290">Int32</span></span>|  
|<span data-ttu-id="aa9d2-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="aa9d2-292">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-292">Int16</span></span>|  
|<span data-ttu-id="aa9d2-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="aa9d2-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="aa9d2-294">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-294">Int16</span></span>|  
|<span data-ttu-id="aa9d2-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-295">NULLABLE</span></span>|<span data-ttu-id="aa9d2-296">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-296">Int16</span></span>|  
|<span data-ttu-id="aa9d2-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-297">REMARKS</span></span>|<span data-ttu-id="aa9d2-298">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-298">String</span></span>|  
|<span data-ttu-id="aa9d2-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="aa9d2-299">COLUMN_DEF</span></span>|<span data-ttu-id="aa9d2-300">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-300">String</span></span>|  
|<span data-ttu-id="aa9d2-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-302">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-302">Int16</span></span>|  
|<span data-ttu-id="aa9d2-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="aa9d2-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="aa9d2-304">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-304">Int16</span></span>|  
|<span data-ttu-id="aa9d2-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="aa9d2-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="aa9d2-306">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-306">Int32</span></span>|  
|<span data-ttu-id="aa9d2-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="aa9d2-308">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-308">Int32</span></span>|  
|<span data-ttu-id="aa9d2-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-309">IS_NULLABLE</span></span>|<span data-ttu-id="aa9d2-310">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-310">String</span></span>|  
|<span data-ttu-id="aa9d2-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="aa9d2-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="aa9d2-312">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-312">String</span></span>|  
|<span data-ttu-id="aa9d2-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="aa9d2-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="aa9d2-314">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-314">String</span></span>|  
|<span data-ttu-id="aa9d2-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-316">Byte</span><span class="sxs-lookup"><span data-stu-id="aa9d2-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="aa9d2-317">Драйвер ODBC для Oracle (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="aa9d2-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="aa9d2-318">Microsoft SQL Server драйвер ODBC для Oracle поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем.</span><span class="sxs-lookup"><span data-stu-id="aa9d2-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="aa9d2-319">Таблицы</span><span class="sxs-lookup"><span data-stu-id="aa9d2-319">Tables</span></span>  
  
-   <span data-ttu-id="aa9d2-320">Столбцы</span><span class="sxs-lookup"><span data-stu-id="aa9d2-320">Columns</span></span>  
  
-   <span data-ttu-id="aa9d2-321">Процедуры</span><span class="sxs-lookup"><span data-stu-id="aa9d2-321">Procedures</span></span>  
  
-   <span data-ttu-id="aa9d2-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="aa9d2-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="aa9d2-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="aa9d2-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="aa9d2-324">Представления</span><span class="sxs-lookup"><span data-stu-id="aa9d2-324">Views</span></span>  
  
-   <span data-ttu-id="aa9d2-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="aa9d2-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="aa9d2-326">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="aa9d2-326">Tables and Views</span></span>  
  
|<span data-ttu-id="aa9d2-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-327">ColumnName</span></span>|<span data-ttu-id="aa9d2-328">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="aa9d2-330">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-330">String</span></span>|  
|<span data-ttu-id="aa9d2-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-331">TABLE_OWNER</span></span>|<span data-ttu-id="aa9d2-332">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-332">String</span></span>|  
|<span data-ttu-id="aa9d2-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-333">TABLE_NAME</span></span>|<span data-ttu-id="aa9d2-334">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-334">String</span></span>|  
|<span data-ttu-id="aa9d2-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-335">TABLE_TYPE</span></span>|<span data-ttu-id="aa9d2-336">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-336">String</span></span>|  
|<span data-ttu-id="aa9d2-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-337">REMARKS</span></span>|<span data-ttu-id="aa9d2-338">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="aa9d2-339">Столбцы</span><span class="sxs-lookup"><span data-stu-id="aa9d2-339">Columns</span></span>  
  
|<span data-ttu-id="aa9d2-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-340">ColumnName</span></span>|<span data-ttu-id="aa9d2-341">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="aa9d2-343">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-343">String</span></span>|  
|<span data-ttu-id="aa9d2-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-344">TABLE_OWNER</span></span>|<span data-ttu-id="aa9d2-345">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-345">String</span></span>|  
|<span data-ttu-id="aa9d2-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-346">TABLE_NAME</span></span>|<span data-ttu-id="aa9d2-347">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-347">String</span></span>|  
|<span data-ttu-id="aa9d2-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-348">COLUMN_NAME</span></span>|<span data-ttu-id="aa9d2-349">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-349">String</span></span>|  
|<span data-ttu-id="aa9d2-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-350">DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-351">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-351">Int16</span></span>|  
|<span data-ttu-id="aa9d2-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-352">TYPE_NAME</span></span>|<span data-ttu-id="aa9d2-353">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-353">String</span></span>|  
|<span data-ttu-id="aa9d2-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-354">PRECISION</span></span>|<span data-ttu-id="aa9d2-355">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-355">Int32</span></span>|  
|<span data-ttu-id="aa9d2-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="aa9d2-356">LENGTH</span></span>|<span data-ttu-id="aa9d2-357">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-357">Int32</span></span>|  
|<span data-ttu-id="aa9d2-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-358">SCALE</span></span>|<span data-ttu-id="aa9d2-359">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-359">Int16</span></span>|  
|<span data-ttu-id="aa9d2-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="aa9d2-360">RADIX</span></span>|<span data-ttu-id="aa9d2-361">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-361">Int16</span></span>|  
|<span data-ttu-id="aa9d2-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-362">NULLABLE</span></span>|<span data-ttu-id="aa9d2-363">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-363">Int16</span></span>|  
|<span data-ttu-id="aa9d2-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-364">REMARKS</span></span>|<span data-ttu-id="aa9d2-365">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-365">String</span></span>|  
|<span data-ttu-id="aa9d2-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="aa9d2-367">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="aa9d2-368">Процедуры</span><span class="sxs-lookup"><span data-stu-id="aa9d2-368">Procedures</span></span>  
  
|<span data-ttu-id="aa9d2-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-369">ColumnName</span></span>|<span data-ttu-id="aa9d2-370">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="aa9d2-372">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-372">String</span></span>|  
|<span data-ttu-id="aa9d2-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="aa9d2-374">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-374">String</span></span>|  
|<span data-ttu-id="aa9d2-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="aa9d2-376">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-376">String</span></span>|  
|<span data-ttu-id="aa9d2-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="aa9d2-378">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-378">Int16</span></span>|  
|<span data-ttu-id="aa9d2-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="aa9d2-380">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-380">Int16</span></span>|  
|<span data-ttu-id="aa9d2-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="aa9d2-382">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-382">Int16</span></span>|  
|<span data-ttu-id="aa9d2-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-383">REMARKS</span></span>|<span data-ttu-id="aa9d2-384">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-384">String</span></span>|  
|<span data-ttu-id="aa9d2-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="aa9d2-386">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="aa9d2-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="aa9d2-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="aa9d2-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-388">ColumnName</span></span>|<span data-ttu-id="aa9d2-389">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="aa9d2-391">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-391">String</span></span>|  
|<span data-ttu-id="aa9d2-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="aa9d2-393">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-393">String</span></span>|  
|<span data-ttu-id="aa9d2-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="aa9d2-395">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-395">String</span></span>|  
|<span data-ttu-id="aa9d2-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-396">COLUMN_NAME</span></span>|<span data-ttu-id="aa9d2-397">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-397">String</span></span>|  
|<span data-ttu-id="aa9d2-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-398">COLUMN_TYPE</span></span>|<span data-ttu-id="aa9d2-399">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-399">Int16</span></span>|  
|<span data-ttu-id="aa9d2-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-400">DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-401">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-401">Int16</span></span>|  
|<span data-ttu-id="aa9d2-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-402">TYPE_NAME</span></span>|<span data-ttu-id="aa9d2-403">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-403">String</span></span>|  
|<span data-ttu-id="aa9d2-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-404">PRECISION</span></span>|<span data-ttu-id="aa9d2-405">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-405">Int32</span></span>|  
|<span data-ttu-id="aa9d2-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="aa9d2-406">LENGTH</span></span>|<span data-ttu-id="aa9d2-407">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-407">Int32</span></span>|  
|<span data-ttu-id="aa9d2-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-408">SCALE</span></span>|<span data-ttu-id="aa9d2-409">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-409">Int16</span></span>|  
|<span data-ttu-id="aa9d2-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="aa9d2-410">RADIX</span></span>|<span data-ttu-id="aa9d2-411">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-411">Int16</span></span>|  
|<span data-ttu-id="aa9d2-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-412">NULLABLE</span></span>|<span data-ttu-id="aa9d2-413">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-413">Int16</span></span>|  
|<span data-ttu-id="aa9d2-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-414">REMARKS</span></span>|<span data-ttu-id="aa9d2-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-415">String</span></span>|  
|<span data-ttu-id="aa9d2-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="aa9d2-416">OVERLOAD</span></span>|<span data-ttu-id="aa9d2-417">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-417">Int32</span></span>|  
|<span data-ttu-id="aa9d2-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="aa9d2-419">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="aa9d2-420">Драйвер ODBC для Jet (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="aa9d2-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="aa9d2-421">Драйвер ODBC для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="aa9d2-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="aa9d2-422">Таблицы</span><span class="sxs-lookup"><span data-stu-id="aa9d2-422">Tables</span></span>  
  
-   <span data-ttu-id="aa9d2-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="aa9d2-423">Indexes</span></span>  
  
-   <span data-ttu-id="aa9d2-424">Столбцы</span><span class="sxs-lookup"><span data-stu-id="aa9d2-424">Columns</span></span>  
  
-   <span data-ttu-id="aa9d2-425">Процедуры</span><span class="sxs-lookup"><span data-stu-id="aa9d2-425">Procedures</span></span>  
  
-   <span data-ttu-id="aa9d2-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="aa9d2-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="aa9d2-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="aa9d2-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="aa9d2-428">Представления</span><span class="sxs-lookup"><span data-stu-id="aa9d2-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="aa9d2-429">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="aa9d2-429">Tables and Views</span></span>  
  
|<span data-ttu-id="aa9d2-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-430">ColumnName</span></span>|<span data-ttu-id="aa9d2-431">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="aa9d2-433">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-433">String</span></span>|  
|<span data-ttu-id="aa9d2-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-434">TABLE_OWNER</span></span>|<span data-ttu-id="aa9d2-435">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-435">String</span></span>|  
|<span data-ttu-id="aa9d2-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-436">TABLE_NAME</span></span>|<span data-ttu-id="aa9d2-437">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-437">String</span></span>|  
|<span data-ttu-id="aa9d2-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-438">TABLE_TYPE</span></span>|<span data-ttu-id="aa9d2-439">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-439">String</span></span>|  
|<span data-ttu-id="aa9d2-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-440">REMARKS</span></span>|<span data-ttu-id="aa9d2-441">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="aa9d2-442">Столбцы</span><span class="sxs-lookup"><span data-stu-id="aa9d2-442">Columns</span></span>  
  
|<span data-ttu-id="aa9d2-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-443">ColumnName</span></span>|<span data-ttu-id="aa9d2-444">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="aa9d2-446">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-446">String</span></span>|  
|<span data-ttu-id="aa9d2-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-447">TABLE_OWNER</span></span>|<span data-ttu-id="aa9d2-448">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-448">String</span></span>|  
|<span data-ttu-id="aa9d2-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-449">TABLE_NAME</span></span>|<span data-ttu-id="aa9d2-450">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-450">String</span></span>|  
|<span data-ttu-id="aa9d2-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-451">COLUMN_NAME</span></span>|<span data-ttu-id="aa9d2-452">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-452">String</span></span>|  
|<span data-ttu-id="aa9d2-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-453">DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-454">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-454">Int16</span></span>|  
|<span data-ttu-id="aa9d2-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-455">TYPE_NAME</span></span>|<span data-ttu-id="aa9d2-456">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-456">String</span></span>|  
|<span data-ttu-id="aa9d2-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-457">PRECISION</span></span>|<span data-ttu-id="aa9d2-458">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-458">Int32</span></span>|  
|<span data-ttu-id="aa9d2-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="aa9d2-459">LENGTH</span></span>|<span data-ttu-id="aa9d2-460">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-460">Int32</span></span>|  
|<span data-ttu-id="aa9d2-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-461">SCALE</span></span>|<span data-ttu-id="aa9d2-462">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-462">Int16</span></span>|  
|<span data-ttu-id="aa9d2-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="aa9d2-463">RADIX</span></span>|<span data-ttu-id="aa9d2-464">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-464">Int16</span></span>|  
|<span data-ttu-id="aa9d2-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-465">NULLABLE</span></span>|<span data-ttu-id="aa9d2-466">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-466">Int16</span></span>|  
|<span data-ttu-id="aa9d2-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-467">REMARKS</span></span>|<span data-ttu-id="aa9d2-468">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-468">String</span></span>|  
|<span data-ttu-id="aa9d2-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="aa9d2-470">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="aa9d2-471">Процедуры</span><span class="sxs-lookup"><span data-stu-id="aa9d2-471">Procedures</span></span>  
  
|<span data-ttu-id="aa9d2-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-472">ColumnName</span></span>|<span data-ttu-id="aa9d2-473">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="aa9d2-475">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-475">String</span></span>|  
|<span data-ttu-id="aa9d2-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="aa9d2-477">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-477">String</span></span>|  
|<span data-ttu-id="aa9d2-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="aa9d2-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-479">String</span></span>|  
|<span data-ttu-id="aa9d2-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="aa9d2-481">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-481">Int16</span></span>|  
|<span data-ttu-id="aa9d2-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="aa9d2-483">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-483">Int16</span></span>|  
|<span data-ttu-id="aa9d2-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="aa9d2-485">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-485">Int16</span></span>|  
|<span data-ttu-id="aa9d2-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-486">REMARKS</span></span>|<span data-ttu-id="aa9d2-487">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-487">String</span></span>|  
|<span data-ttu-id="aa9d2-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="aa9d2-489">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="aa9d2-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="aa9d2-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="aa9d2-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-491">ColumnName</span></span>|<span data-ttu-id="aa9d2-492">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="aa9d2-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-494">String</span></span>|  
|<span data-ttu-id="aa9d2-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa9d2-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="aa9d2-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-496">String</span></span>|  
|<span data-ttu-id="aa9d2-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="aa9d2-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-498">String</span></span>|  
|<span data-ttu-id="aa9d2-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-499">COLUMN_NAME</span></span>|<span data-ttu-id="aa9d2-500">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-500">String</span></span>|  
|<span data-ttu-id="aa9d2-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-501">COLUMN_TYPE</span></span>|<span data-ttu-id="aa9d2-502">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-502">Int16</span></span>|  
|<span data-ttu-id="aa9d2-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-503">DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-504">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-504">Int16</span></span>|  
|<span data-ttu-id="aa9d2-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-505">TYPE_NAME</span></span>|<span data-ttu-id="aa9d2-506">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-506">String</span></span>|  
|<span data-ttu-id="aa9d2-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-507">PRECISION</span></span>|<span data-ttu-id="aa9d2-508">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-508">Int32</span></span>|  
|<span data-ttu-id="aa9d2-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="aa9d2-509">LENGTH</span></span>|<span data-ttu-id="aa9d2-510">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-510">Int32</span></span>|  
|<span data-ttu-id="aa9d2-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-511">SCALE</span></span>|<span data-ttu-id="aa9d2-512">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-512">Int16</span></span>|  
|<span data-ttu-id="aa9d2-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="aa9d2-513">RADIX</span></span>|<span data-ttu-id="aa9d2-514">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-514">Int16</span></span>|  
|<span data-ttu-id="aa9d2-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-515">NULLABLE</span></span>|<span data-ttu-id="aa9d2-516">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-516">Int16</span></span>|  
|<span data-ttu-id="aa9d2-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-517">REMARKS</span></span>|<span data-ttu-id="aa9d2-518">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-518">String</span></span>|  
|<span data-ttu-id="aa9d2-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="aa9d2-519">OVERLOAD</span></span>|<span data-ttu-id="aa9d2-520">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-520">Int32</span></span>|  
|<span data-ttu-id="aa9d2-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="aa9d2-522">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="aa9d2-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="aa9d2-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="aa9d2-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="aa9d2-524">ColumnName</span></span>|<span data-ttu-id="aa9d2-525">DataType</span><span class="sxs-lookup"><span data-stu-id="aa9d2-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="aa9d2-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="aa9d2-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="aa9d2-527">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-527">String</span></span>|  
|<span data-ttu-id="aa9d2-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="aa9d2-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="aa9d2-529">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-529">String</span></span>|  
|<span data-ttu-id="aa9d2-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="aa9d2-531">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-531">String</span></span>|  
|<span data-ttu-id="aa9d2-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-532">COLUMN_NAME</span></span>|<span data-ttu-id="aa9d2-533">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-533">String</span></span>|  
|<span data-ttu-id="aa9d2-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-534">COLUMN_TYPE</span></span>|<span data-ttu-id="aa9d2-535">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-535">Int16</span></span>|  
|<span data-ttu-id="aa9d2-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-536">DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-537">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-537">Int16</span></span>|  
|<span data-ttu-id="aa9d2-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="aa9d2-538">TYPE_NAME</span></span>|<span data-ttu-id="aa9d2-539">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-539">String</span></span>|  
|<span data-ttu-id="aa9d2-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-540">COLUMN_SIZE</span></span>|<span data-ttu-id="aa9d2-541">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-541">Int32</span></span>|  
|<span data-ttu-id="aa9d2-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="aa9d2-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="aa9d2-543">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-543">Int32</span></span>|  
|<span data-ttu-id="aa9d2-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="aa9d2-545">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-545">Int16</span></span>|  
|<span data-ttu-id="aa9d2-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="aa9d2-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="aa9d2-547">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-547">Int16</span></span>|  
|<span data-ttu-id="aa9d2-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-548">NULLABLE</span></span>|<span data-ttu-id="aa9d2-549">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-549">Int16</span></span>|  
|<span data-ttu-id="aa9d2-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="aa9d2-550">REMARKS</span></span>|<span data-ttu-id="aa9d2-551">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-551">String</span></span>|  
|<span data-ttu-id="aa9d2-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="aa9d2-552">COLUMN_DEF</span></span>|<span data-ttu-id="aa9d2-553">Строковое</span><span class="sxs-lookup"><span data-stu-id="aa9d2-553">String</span></span>|  
|<span data-ttu-id="aa9d2-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="aa9d2-555">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-555">Int16</span></span>|  
|<span data-ttu-id="aa9d2-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="aa9d2-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="aa9d2-557">Int16</span><span class="sxs-lookup"><span data-stu-id="aa9d2-557">Int16</span></span>|  
|<span data-ttu-id="aa9d2-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="aa9d2-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="aa9d2-559">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-559">Int32</span></span>|  
|<span data-ttu-id="aa9d2-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="aa9d2-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="aa9d2-561">Int32</span><span class="sxs-lookup"><span data-stu-id="aa9d2-561">Int32</span></span>|  
|<span data-ttu-id="aa9d2-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="aa9d2-562">IS_NULLABLE</span></span>|<span data-ttu-id="aa9d2-563">Строка</span><span class="sxs-lookup"><span data-stu-id="aa9d2-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa9d2-564">См. также</span><span class="sxs-lookup"><span data-stu-id="aa9d2-564">See Also</span></span>  
 [<span data-ttu-id="aa9d2-565">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aa9d2-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
