# Compilation Unit
- [ ] CompilationUnit:
	- [x] OrdinaryCompilationUnit
	- [ ] CompactCompilationUnit
	- [ ] ModularCompilationUnit

- [ ] OrdinaryCompilationUnit: 
	- [ ] \[PackageDeclaration\] {ImportDeclaration} {TopLevelClassOrInterfaceDeclaration}
		- [ ] package declaration
		- [ ] import declaration
		- [x] Top level class or interface declaration

# Classes
- [x] TopLevelClassOrInterfaceDeclaration: 
	- [x] ClassDeclaration
	- [x] InterfaceDeclaration
	- [x] ;

- [x] ClassDeclaration: 
	- [x] NormalClassDeclaration
	- [x] EnumDeclaration
	- [x] RecordDeclaration

- [x] InterfaceDeclaration: 
	- [x] NormalInterfaceDeclaration 
	- [x] AnnotationInterfaceDeclaration

### Regular classes
- [ ] NormalClassDeclaration:
	- [ ] {ClassModifier} class TypeIdentifier \[TypeParameters\] \[ClassExtends\] \[ClassImplements\] \[ClassPermits\] ClassBody
		- [x] class modifiers
		- [x] type identifier
			- [x] make sure it's not `permits`, `record`, `sealed`, `var`, or `yield`
		- [ ] type parameters
		- [x] extends list
		- [x] implements list
		- [x] permits list
		- [x] body

- [x] ClassModifier: 
	- [x] Annotation
	- [x] public
	- [x] protected
	- [x] private
	- [x] abstract
	- [x] static
	- [x] final
	- [x] sealed
	- [x] non-sealed
	- [x] strictfp

- [x] ClassExtends: 
	- [x] extends ClassType

- [x] ClassImplements: 
	- [x] implements InterfaceTypeList

- [x] InterfaceTypeList:
	- [x] InterfaceType {, InterfaceType}

- [x] ClassPermits: 
	- [x] permits TypeName {, TypeName}

- [x] ClassBody: 
	- [x] { {ClassBodyDeclaration} } 

- [x] ClassBodyDeclaration: 
	- [x] ClassMemberDeclaration
	- [x] InstanceInitializer
	- [x] StaticInitializer
	- [x] ConstructorDeclaration

- [x]  ClassMemberDeclaration: 
	- [x] FieldDeclaration
	- [x] MethodDeclaration
	- [x] ClassDeclaration
	- [x] InterfaceDeclaration
	- [x] ;

- [x] FieldDeclaration:
	- [x] {FieldModifier} UnannType VariableDeclaratorList ;

- [x] FieldModifier:
	- [x] Annotation
	- [x] public
	- [x] protected
	- [x] private
	- [x] static
	- [x] final
	- [x] transient
	- [x] volatile

- [x] ConstructorDeclaration:
	- [x] {ConstructorModifier} ConstructorDeclarator \[Throws\] ConstructorBody 
		- [x] modifiers
		- [x] declarator
		- [x] throws
		- [x] body

- [ ] ConstructorDeclarator: 
	- [ ] \[TypeParameters\] TypeIdentifier ( \[ReceiverParameter ,\] \[FormalParameterList\] )
		- [ ] type parameters
		- [x] name
		- [ ] receiver parameter
		- [x] formal parameter list

- [x] ConstructorBody: 
	- [x] { \[BlockStatements\] ConstructorInvocation \[BlockStatements\] } 
	- [x] { \[BlockStatements\] }

- [ ] ConstructorInvocation: 
	- [x] \[TypeArguments\] this ( \[ArgumentList\] ) ; 
		- [ ] type args
	- [ ] \[TypeArguments\] super ( \[ArgumentList\] ) ; 
	- [ ] ExpressionName . \[TypeArguments\] super ( \[ArgumentList\] ) ; 
	- [ ] Primary . \[TypeArguments\] super ( \[ArgumentList\] ) ;

- [x] ConstructorModifier:
	- [x] annotation
	- [x] public
	- [x] protected
	- [x] private

### Records
- [ ] RecordDeclaration: 
	- [ ] {ClassModifier} record TypeIdentifier \[TypeParameters\] RecordHeader \[ClassImplements\] RecordBody
		- [x] modifiers
		- [x] identifier
		- [ ] type parameters
		- [x] header
		- [x] implements
		- [x] body

- [x] RecordHeader:
	- [x] ( \[RecordComponentList\] ) 

- [x] RecordComponentList:
	- [x] RecordComponent {, RecordComponent} 

- [x] RecordComponent: 
	- [x] {RecordComponentModifier} UnannType Identifier
	- [x] VariableArityRecordComponent 

- [ ] VariableArityRecordComponent: 
	- [ ] {RecordComponentModifier} UnannType {Annotation} ... Identifier 
		- [x] modifier before type
		- [ ] annotation after type

- [x] RecordComponentModifier:
	- [x] Annotation

- [x] RecordBody: 
	- [x] { {RecordBodyDeclaration} }

- [x] RecordBodyDeclaration: 
	- [x] ClassBodyDeclaration 
	- [x] CompactConstructorDeclaration

- [x] CompactConstructorDeclaration: 
	- [x] {ConstructorModifier} SimpleTypeName ConstructorBody
		- [x] modifier
### Enums
- [x] EnumDeclaration: 
	- [x] {ClassModifier} enum TypeIdentifier \[ClassImplements\] EnumBody
		- [x] modifier
		- [x] identifier
		- [x] implements
		- [x] body

- [x] EnumBody: 
	- [x] { \[EnumConstantList\] \[,\] \[EnumBodyDeclarations\] } 

- [x] EnumConstantList: 
	- [x] EnumConstant {, EnumConstant} 

- [x] EnumConstant:
	- [x] {EnumConstantModifier} Identifier \[( \[ArgumentList\] )\] \[ClassBody\] 
		- [x] modifier
		- [x] args
		- [x] body

- [x] EnumConstantModifier:
	- [x] Annotation

- [x] EnumBodyDeclarations:
	- [x] ; {ClassBodyDeclaration}
# Interfaces
- [x] InterfaceDeclaration:
	- [x] NormalInterfaceDeclaration
	- [x] AnnotationInterfaceDeclaration
### Normal Interface
- [ ] NormalInterfaceDeclaration:
	- [ ] {InterfaceModifier} interface TypeIdentifier \[TypeParameters\] \[InterfaceExtends\] \[InterfacePermits\] InterfaceBody
		- [x] modifiers
		- [x] identifier
		- [ ] type parameters
		- [x] extends list
		- [x] permits list
		- [x] body

- [x] InterfaceModifier: 
	- [x] Annotation
	- [x] public
	- [x] protected
	- [x] private
	- [x] abstract
	- [x] static
	- [x] sealed
	- [x] non-sealed
	- [x] strictfp

- [x] InterfaceExtends: 
	- [x] extends InterfaceTypeList

- [x] InterfacePermits: 
	- [x] permits TypeName {, TypeName}

- [x] InterfaceBody: 
	- [x] { {InterfaceMemberDeclaration} } 

- [x] InterfaceMemberDeclaration:
	- [x] ConstantDeclaration
	- [x] InterfaceMethodDeclaration
	- [x] ClassDeclaration
	- [x] InterfaceDeclaration
	- [x] ;

- [x] ConstantDeclaration: 
	- [x] {ConstantModifier} UnannType VariableDeclaratorList ; 

- [x] ConstantModifier:
	- [x] Annotation
	- [x] public
	- [x] static
	- [x] final

- [x] InterfaceMethodDeclaration:
	- [x] {InterfaceMethodModifier} MethodHeader MethodBody 

- [x] InterfaceMethodModifier:
	- [x] Annotation
	- [x] public
	- [x] private
	- [x] abstract
	- [x] default
	- [x] static
	- [x] strictfp
### Annotation Interface
- [x] AnnotationInterfaceDeclaration: 
	- [x] {InterfaceModifier} @ interface TypeIdentifier AnnotationInterfaceBody

- [x] AnnotationInterfaceBody:
	- [x] { {AnnotationInterfaceMemberDeclaration} } 

- [x] AnnotationInterfaceMemberDeclaration: 
	- [x] AnnotationInterfaceElementDeclaration
	- [x] ConstantDeclaration
	- [x] ClassDeclaration
	- [x] InterfaceDeclaration
	- [x] ;

- [ ] AnnotationInterfaceElementDeclaration: 
	- [ ] {AnnotationInterfaceElementModifier} UnannType Identifier ( ) \[Dims\] \[DefaultValue\] ; 
		- [x] modifier
		- [x] type
		- [x] identifier
		- [ ] dims
		- [x] default value

- [x] AnnotationInterfaceElementModifier: 
	- [x] Annotation
	- [x] public
	- [x] abstract

- [x] DefaultValue: 
	- [x] default ElementValue

- [x] Annotation: 
	- [x] NormalAnnotation
	- [x] MarkerAnnotation
	- [x] SingleElementAnnotation

- [x] MarkerAnnotation:
	- [x] @ TypeName

- [x] SingleElementAnnotation: 
	- [x] @ TypeName ( ElementValue )

- [x] NormalAnnotation:
	- [x] @ TypeName ( \[ElementValuePairList\] ) 

- [x] ElementValuePairList: 
	- [x] ElementValuePair {, ElementValuePair}

- [x] ElementValuePair:
	- [x] Identifier = ElementValue 

- [x] ElementValue: 
	- [x] ConditionalExpression
	- [x] ElementValueArrayInitializer
	- [x] Annotation

- [x] ElementValueArrayInitializer:
	- [x] { \[ElementValueList\] \[,\] } 

- [x] ElementValueList:
	- [x] ElementValue {, ElementValue}
# Methods
- [ ] MethodDeclaration:
	- [ ] {MethodModifier} MethodHeader MethodBody
		- [x] modifier
		- [ ] header (doing it inline, not a separate function, so depends on below list)
		- [x] body
- [x] MethodModifier: 
	- [x] Annotation
	- [x] public
	- [x] protected
	- [x] private
	- [x] abstract
	- [x] static
	- [x] final
	- [x] synchronized
	- [x] native
	- [x] strictfp
- [ ] MethodHeader:
	- [ ] Result MethodDeclarator \[Throws\] 
		- [x] result
		- [ ] method declarator (doing it inline, not a separate function, so depends on below list)
		- [x] throws
	- [ ] TypeParameters {Annotation} Result MethodDeclarator \[Throws\]
		- [ ] type parameters
		- [ ] annotations
		- [ ] result
		- [ ] method declarator (doing it inline, not a separate function, so depends on below list)
		- [ ] throws
- [x] Result:
	- [x] UnannType
	- [x] void
- [ ] MethodDeclarator:
	- [ ] Identifier ( \[ReceiverParameter ,\] \[FormalParameterList\] ) \[Dims\]
		- [x] identifier
		- [ ] receiver parameter  (doing it inline, not a separate function, so depends on below list)
		- [x] formal paramter list
		- [ ] dims  (doing it inline, not a separate function, so depends on below list)
- [x] FormalParameterList: 
	- [x] FormalParameter {, FormalParameter}
- [ ] FormalParameter: 
	- [ ] {VariableModifier} UnannType VariableDeclaratorId
		- [x] modifiers
			- [x] annotation
			- [x] final
		- [x] type
		- [ ] variable declarator id (currently just plain identifier, no dims)
	- [x] VariableArityParameter
- [ ] VariableArityParameter:
	- [ ] {VariableModifier} UnannType {Annotation} ... Identifier
		- [x] modifiers
			- [x] annotation
			- [x] final
		- [x] type
		- [ ] annotations
		- [x] identifier

- [x] Throws: 
	- [x] throws ExceptionTypeList 

- [x] ExceptionTypeList:
	- [x] ExceptionType {, ExceptionType}

- [ ] ExceptionType:
	- [x] ClassType
	- [ ] TypeVariable

- [x] MethodBody: 
	- [x] Block 
	- [x] ;
# Statements
- [x] Block:
	- [x] { \[BlockStatements\] }

- [x] BlockStatements: 
	- [x] BlockStatement {BlockStatement} 

- [ ] BlockStatement:
	- [ ] LocalClassOrInterfaceDeclaration
	- [x] LocalVariableDeclarationStatement
	- [x] Statement

- [ ] LocalClassOrInterfaceDeclaration:
	- [ ] ClassDeclaration
	- [ ] NormalInterfaceDeclaration

- [x] LocalVariableDeclarationStatement:
	- [x] LocalVariableDeclaration ;

- [x] LocalVariableDeclaration:
	- [x] {VariableModifier} LocalVariableType VariableDeclaratorList
		- [x] type + declarator list
		- [x] modifiers
			- [x] annotation
			- [x] final

- [x] Statement:
	- [x] StatementWithoutTrailingSubstatement
	- [x] LabeledStatement
	- [x] IfThenStatement
	- [x] IfThenElseStatement
	- [x] WhileStatement
	- [x] ForStatement

- [x] StatementNoShortIf:
	- [x] StatementWithoutTrailingSubstatement
	- [x] LabeledStatementNoShortIf
	- [x] IfThenElseStatementNoShortIf
	- [x] WhileStatementNoShortIf
	- [x] ForStatementNoShortIf

- [x] StatementWithoutTrailingSubstatement:
	- [x] Block
	- [x] EmptyStatement
	- [x] ExpressionStatement
	- [x] AssertStatement
	- [x] SwitchStatement
	- [x] DoStatement
	- [x] BreakStatement
	- [x] ContinueStatement
	- [x] ReturnStatement
	- [x] SynchronizedStatement
	- [x] ThrowStatement
	- [x] TryStatement
	- [x] YieldStatement

- [x] EmptyStatement: 
	- [x] ;

- [x] ExpressionStatement: 
	- [x] StatementExpression ;

- [x] StatementExpression:
	- [x] Assignment
	- [x] PreIncrementExpression
	- [x] PreDecrementExpression
	- [x] PostIncrementExpression
	- [x] PostDecrementExpression
	- [x] MethodInvocation
	- [x] ClassInstanceCreationExpression

- [x] Assignment:
	- [x] LeftHandSide AssignmentOperator Expression

- [x] LeftHandSide: 
	- [x] ExpressionName
	- [x] FieldAccess
	- [x] ArrayAccess

- [x] AssignmentOperator: 
	- [x] = 
	- [x] \*= 
	- [x] /= 
	- [x] %= 
	- [x] += 
	- [x] -= 
	- [x] <<= 
	- [x] \>\>= 
	- [x] \>\>\>= 
	- [x] &= 
	- [x] ^= 
	- [x] |= 

- [x] VariableDeclaratorList:
	- [x] VariableDeclarator {, VariableDeclarator}

- [x] VariableDeclarator: 
	- [x] Va1riableDeclaratorId \[= VariableInitializer\]

- [ ] VariableDeclaratorId: 
	- [ ] Identifier \[Dims\]
		- [x] identifier
		- [ ] dims
	- [ ] _

- [x] TryStatement:
	- [x] try Block Catches 
	- [x] try Block \[Catches\] Finally
	- [x] TryWithResourcesStatement 

- [x] Catches: 
	- [x] CatchClause {CatchClause}

- [x] CatchClause: 
	- [x] catch ( CatchFormalParameter ) Block 

- [x] CatchFormalParameter:
	- [x] {VariableModifier} CatchType VariableDeclaratorId
		- [x] modifiers

- [x] CatchType:
	- [x] UnannClassType {| ClassType} 

- [x] Finally:
	- [x] finally Block

- [x] ForStatement:
	- [x] BasicForStatement
	- [x] EnhancedForStatement

- [x] BasicForStatement:
	- [x] for ( \[ForInit\] ; \[Expression\] ; \[ForUpdate\] ) Statement 

- [x] ForInit: 
	- [x] StatementExpressionList 
	- [x] LocalVariableDeclaration

- [x] ForUpdate:
	- [x] StatementExpressionList

- [x] StatementExpressionList:
	- [x] StatementExpression {, StatementExpression}

- [x] EnhancedForStatement:
	- [x] for ( LocalVariableDeclaration : Expression ) Statement 

- [x] SynchronizedStatement:
	- [x] synchronized ( Expression ) Block

- [x] YieldStatement: 
	- [x] yield Expression ;

- [x] SwitchStatement: 
	- [x] switch ( Expression ) SwitchBlock

- [x] SwitchBlock: 
	- [x] { SwitchRule {SwitchRule} }
	- [x] { {SwitchBlockStatementGroup} {SwitchLabel :} }
		- [x] statement group
		- [x] trailing labels

- [x] SwitchRule:
	- [x] SwitchLabel -> Expression ; 
	- [x] SwitchLabel -> Block 
	- [x] SwitchLabel -> ThrowStatement 

	- [x]  :
	- [x] SwitchLabel : {SwitchLabel :} BlockStatements

- [x] SwitchLabel:
	- [x] case CaseConstant {, CaseConstant}
	- [x] case null \[, default\] 
	- [x] case CasePattern {, CasePattern} \[Guard\]
		- [x] pattern
		- [x] guard
	- [x] default

- [x] CaseConstant:
	- [x] ConditionalExpression

- [x] CasePattern: 
	- [x] Pattern

- [x] Pattern: 
	- [x] TypePattern
	- [x] RecordPattern

- [x] TypePattern: 
	- [x] LocalVariableDeclaration

- [x] RecordPattern:
	- [x] ReferenceType ( \[ComponentPatternList\] )

- [x] ComponentPatternList: 
	- [x] ComponentPattern {, ComponentPattern }

- [x] ComponentPattern:
	- [x] Pattern 
	- [x] MatchAllPattern

- [x] MatchAllPattern:
	- [x] _

- [x] Guard: 
	- [x] when Expression
### Expressions
- [ ] Expression:
	- [ ] LambdaExpression
	- [x] AssignmentExpression

- [x]  AssignmentExpression:
	- [x] ConditionalExpression
	- [x] Assignment

- [ ] ConditionalExpression: 
	- [x] ConditionalOrExpression
	- [x] ConditionalOrExpression ? Expression : ConditionalExpression 
	- [ ] ConditionalOrExpression ? Expression : LambdaExpression

- [x] ConditionalOrExpression: 
	- [x] ConditionalAndExpression 
	- [x] ConditionalOrExpression || ConditionalAndExpression

- [x] ConditionalAndExpression: 
	- [x] InclusiveOrExpression 
	- [x] ConditionalAndExpression && InclusiveOrExpression

- [x] InclusiveOrExpression: 
	- [x] ExclusiveOrExpression
	- [x] InclusiveOrExpression | ExclusiveOrExpression

- [x] ExclusiveOrExpression:
	- [x] AndExpression
	- [x] ExclusiveOrExpression ^ AndExpression
 
- [x] AndExpression:
	- [x] EqualityExpression 
	- [x] AndExpression & EqualityExpression
 
- [x] EqualityExpression:
	- [x] RelationalExpression
	- [x] EqualityExpression == RelationalExpression
	- [x] EqualityExpression != RelationalExpression

- [ ] RelationalExpression:
	- [x] ShiftExpression
	- [x] RelationalExpression < ShiftExpression
	- [x] RelationalExpression > ShiftExpression
	- [x] RelationalExpression <= ShiftExpression
	- [x] RelationalExpression >= ShiftExpression
	- [ ] InstanceofExpression 

- [ ] InstanceofExpression: 
	- [ ] RelationalExpression instanceof ReferenceType
	- [ ] RelationalExpression instanceof Pattern

- [x] ShiftExpression: 
	- [x] AdditiveExpression 
	- [x] ShiftExpression << AdditiveExpression
	- [x] ShiftExpression >> AdditiveExpression
	- [x] ShiftExpression >>> AdditiveExpression

- [x] AdditiveExpression:
	- [x] MultiplicativeExpression 
	- [x] AdditiveExpression + MultiplicativeExpression
	- [x] AdditiveExpression - MultiplicativeExpression

- [x] MultiplicativeExpression:
	- [x] UnaryExpression
	- [x] MultiplicativeExpression * UnaryExpression
	- [x] MultiplicativeExpression / UnaryExpression
	- [x] MultiplicativeExpression % UnaryExpression

- [x] UnaryExpression:
	- [x] PreIncrementExpression 
	- [x] PreDecrementExpression 
	- [x] \+ UnaryExpression 
	- [x] \- UnaryExpression 
	- [x] UnaryExpressionNotPlusMinus 

- [x] PreIncrementExpression: 
	- [x] ++ UnaryExpression 

- [x] PreDecrementExpression:
	- [x] -- UnaryExpression 

- [ ] UnaryExpressionNotPlusMinus: 
	- [x] PostfixExpression 
	- [x] ~ UnaryExpression 
	- [x] ! UnaryExpression 
	- [ ] CastExpression
	- [x] SwitchExpression

- [x] PostfixExpression: 
	- [x] Primary
	- [x] ExpressionName
	- [x] PostIncrementExpression
	- [x] PostDecrementExpression
- [x] ExpressionName: 
	- [x] Identifier 
	- [x] AmbiguousName . Identifier
- [x] PostIncrementExpression: 
	- [x] PostfixExpression ++

- [x] PostDecrementExpression:
	- [x] PostfixExpression --

- [x] Primary:
	- [x] PrimaryNoNewArray
	- [x] ArrayCreationExpression

- [x] PrimaryNoNewArray: 
	- [x] Literal
	- [x] ClassLiteral
	- [x] this
	- [x] TypeName . this 
	- [x] ( Expression )
	- [x] ClassInstanceCreationExpression
	- [x] FieldAccess
	- [x] ArrayAccess
	- [x] MethodInvocation
	- [x] MethodReference

- [x] ClassLiteral: 
	- [x] TypeName {[ ]} . class
	- [x] NumericType {[ ]} . class
	- [x] boolean {[ ]} . class 
	- [x] void . class

- [ ] ClassInstanceCreationExpression:
	- [x] UnqualifiedClassInstanceCreationExpression
	- [ ] ExpressionName . UnqualifiedClassInstanceCreationExpression
	- [ ] Primary . UnqualifiedClassInstanceCreationExpression

- [ ] UnqualifiedClassInstanceCreationExpression:
	- [ ] new \[TypeArguments\] ClassOrInterfaceTypeToInstantiate ( \[ArgumentList\] ) \[ClassBody\]
		- [ ] type args
		- [x] args list
		- [ ] class body

- [ ] ClassOrInterfaceTypeToInstantiate:
	- [ ] {Annotation} Identifier {. {Annotation} Identifier} \[TypeArgumentsOrDiamond\]

- [ ] FieldAccess: 
	- [x] Primary . Identifier 
	- [ ] super . Identifier
	- [ ] TypeName . super . Identifier

- [x] ArrayCreationExpression:
	- [x] ArrayCreationExpressionWithoutInitializer
	- [x] ArrayCreationExpressionWithInitializer 

- [x] ArrayCreationExpressionWithoutInitializer:
	- [x] new PrimitiveType DimExprs \[Dims\]
	- [x] new ClassOrInterfaceType DimExprs \[Dims\]

- [x] ArrayCreationExpressionWithInitializer:
	- [x] new PrimitiveType Dims ArrayInitializer
	- [x] new ClassOrInterfaceType Dims ArrayInitializer

- [x] DimExprs:
	- [x] DimExpr {DimExpr}

- [ ] DimExpr:
	- [ ] {Annotation} \[ Expression \]

- [x] ArrayInitializer: 
	- [x] { \[VariableInitializerList\] \[,\] } 

- [x] VariableInitializerList: 
	- [x] VariableInitializer {, VariableInitializer} 

- [x] ArrayAccess: 
	- [x] ExpressionName \[ Expression \]
	- [x] PrimaryNoNewArray \[ Expression \] 
	- [x] ArrayCreationExpressionWithInitializer \[ Expression \]

- [ ] MethodInvocation: 
	- [x] MethodName ( \[ArgumentList\] ) 
	- [ ] TypeName . \[TypeArguments\] Identifier ( \[ArgumentList\] )
	- [ ] ExpressionName . \[TypeArguments\] Identifier ( \[ArgumentList\] ) 
	- [ ] Primary . \[TypeArguments\] Identifier ( \[ArgumentList\] )
	- [ ] super . \[TypeArguments\] Identifier ( \[ArgumentList\] )
	- [ ] TypeName . super . \[TypeArguments\] Identifier ( \[ArgumentList\] )

- [ ] MethodReference: 
	- [ ] ExpressionName :: \[TypeArguments\] Identifier 
	- [ ] Primary :: \[TypeArguments\] Identifier
	- [ ] ReferenceType :: \[TypeArguments\] Identifier 
	- [ ] super :: \[TypeArguments\] Identifier 
	- [ ] TypeName . super :: \[TypeArguments\] Identifier 
	- [ ] ClassType :: \[TypeArguments\] new
	- [x] ArrayType :: new

- [x] SwitchExpression: 
	- [x] switch ( Expression ) SwitchBlock
# Types
- [x] Type:
	- [x] PrimitiveType
	- [x] ReferenceType
- [ ] ReferenceType:
	- [x] ClassOrInterfaceType 
	- [ ] TypeVariable
	- [x] ArrayType

- [x] ClassOrInterfaceType:
	- [x] ClassType 
	- [x] InterfaceType

- [ ] ClassType: 
	- [ ] {Annotation} TypeIdentifier \[TypeArguments\] 
	- [ ] PackageName . {Annotation} TypeIdentifier \[TypeArguments\]
	- [ ] ClassOrInterfaceType . {Annotation} TypeIdentifier \[TypeArguments\]

- [x] InterfaceType:
	- [x] ClassType

- [ ] TypeVariable:
	- [ ] {Annotation} TypeIdentifier 

- [ ] ArrayType: 
	- [ ] PrimitiveType Dims
	- [ ] ClassOrInterfaceType Dims
	- [ ] TypeVariable Dims

- [ ] Dims:
	- [ ] {Annotation} \[ \] {{Annotation} \[ \]}


- [ ] UnannType: 
	- [ ] UnannPrimitiveType 
	- [ ] UnannReferenceType

- [ ] UnannPrimitiveType: 
	- [ ] NumericType
	- [ ] boolean

- [ ] UnannReferenceType: 
	- [ ] UnannClassOrInterfaceType 
	- [ ] UnannTypeVariable
	- [ ] UnannArrayType

- [ ] UnannClassOrInterfaceType: 
	- [ ] UnannClassType
	- [ ] UnannInterfaceType

- [ ] UnannClassType:
	- [ ] TypeIdentifier \[TypeArguments\] 
	- [ ] PackageName . {Annotation} TypeIdentifier \[TypeArguments\] 
	- [ ] UnannClassOrInterfaceType . {Annotation} TypeIdentifier \[TypeArguments\]

- [ ] UnannInterfaceType:
	- [ ] UnannClassType 

- [ ] UnannTypeVariable: 
	- [ ] TypeIdentifier

- [ ] UnannArrayType:
	- [ ] UnannPrimitiveType Dims
	- [ ] UnannClassOrInterfaceType Dims
	- [ ] UnannTypeVariable Dims

# Names
All of these are just lists of identifiers
- [ ] ModuleName:
	- [ ] Identifier
	- [ ] ModuleName . Identifier 

- [ ] PackageName: 
	- [ ] Identifier
	- [ ] PackageName . Identifier 

- [ ] TypeName: 
	- [ ] TypeIdentifier
	- [ ] PackageOrTypeName . TypeIdentifier

- [ ] PackageOrTypeName: 
	- [ ] Identifier
	- [ ] PackageOrTypeName . Identifier

- [ ] ExpressionName: 
	- [ ] Identifier
	- [ ] AmbiguousName . Identifier 

- [ ] MethodName: 
	- [ ] UnqualifiedMethodIdentifier

- [ ] AmbiguousName: 
	- [ ] Identifier
	- [ ] AmbiguousName . Identifier

- [ ] TypeIdentifier:
	- [ ] Identifier 
		- [ ] but not permits, record, sealed, var, or yield

- [ ] UnqualifiedMethodIdentifier: 
	- [ ] Identifier 
		- [ ] but not yield