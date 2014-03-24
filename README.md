Spring-AOP_transaction_management-Hibernate-Example
===================================================

Spring AOP transaction management in Hibernate

http://www.mkyong.com/spring/spring-aop-transaction-management-in-hibernate/



1. Table creation

MySQL table scripts, a ‘product‘ table and a ‘product quantity on hand‘ table.

CREATE TABLE  `mkyong`.`product` (
  `PRODUCT_ID` BIGINT(20) UNSIGNED NOT NULL AUTO_INCREMENT,
  `PRODUCT_CODE` VARCHAR(20) NOT NULL,
  `PRODUCT_DESC` VARCHAR(255) NOT NULL,
  PRIMARY KEY (`PRODUCT_ID`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8;

CREATE TABLE  `mkyong`.`product_qoh` (
  `QOH_ID` BIGINT(20) UNSIGNED NOT NULL AUTO_INCREMENT,
  `PRODUCT_ID` BIGINT(20) UNSIGNED NOT NULL,
  `QTY` INT(10) UNSIGNED NOT NULL,
  PRIMARY KEY (`QOH_ID`),
  KEY `FK_product_qoh_product_id` (`PRODUCT_ID`),
  CONSTRAINT `FK_product_qoh_product_id` FOREIGN KEY (`PRODUCT_ID`)
  REFERENCES `product` (`PRODUCT_ID`)
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8;