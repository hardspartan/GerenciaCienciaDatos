# 📜 Gobernanza de Datos

## Descripción
Este documento detalla las políticas y estándares de gobernanza de datos implementados en el proyecto de predicción de precios de ganado. Su propósito es garantizar la seguridad, integridad y calidad de los datos utilizados.

## 1. Normas y Estándares Aplicados
Para asegurar la correcta gestión de los datos, se siguen las siguientes normas:
- **ISO 27001**: Estándar para la seguridad de la información.
- **GDPR (Reglamento General de Protección de Datos)**: Aplicado en caso de manejo de datos personales.
- **AWS Well-Architected Framework**: Buenas prácticas para la gobernanza de datos en la nube.

## 2. Privacidad y Seguridad de Datos
Para proteger la confidencialidad e integridad de los datos, se aplican las siguientes medidas:
- **Control de Accesos**: Uso de roles y permisos en AWS IAM para restringir acceso.
- **Encriptación de Datos**: Aplicación de cifrado en reposo y en tránsito mediante AWS KMS y TLS.
- **Anonimización**: Eliminación de datos sensibles en datasets compartidos para análisis.
- **Registro y Monitoreo**: Uso de AWS CloudTrail para auditoría de accesos y modificaciones.

## 3. Control y Auditoría de Datos
Para garantizar la trazabilidad y control de cambios en los datos, se implementan las siguientes estrategias:
- **Versionado de Datos**: Control de versiones en `data/processed/` con registros de modificaciones.
- **Monitoreo de Calidad**: Validación periódica de datos en `data/validation/` antes de modelado.
- **Auditoría de Uso**: Revisión de logs de acceso y actividad en sistemas de almacenamiento.

Estas prácticas aseguran que los datos sean confiables, seguros y cumplan con los requisitos de calidad para la toma de decisiones basada en modelos predictivos.

