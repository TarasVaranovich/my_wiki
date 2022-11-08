Applying CQRS pattern in our system expect the following benefits:           
- performance increase due to optimized data schemas
- get rid of extra validations and checks
- independent scaling
- security increase (separate rights for write and read data, full separation on model level)
- absence of _heisenbug_ (the bug when failure changes its properties and/or behavior during attempt to detect it)
- improvement of evolution and maintenance (more maintainable and flexible models)