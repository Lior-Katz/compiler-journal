	# Statements
- [x] Block: (currently only in the context of method body)
	- [x] { \[BlockStatements\] }

- [x] BlockStatements: 
	- [x] BlockStatement {BlockStatement} 

- [x] BlockStatement:
	- [ ] LocalClassOrInterfaceDeclaration
	- [x] LocalVariableDeclarationOrStatement

- [x] LocalVariableDeclarationOrStatement
	- [x] EmptyStatement
	- [x] Block
	- [x] PrefixExpressionStatement
	- [x] SimpleStatement
	- [x] StatementStartingWithName

- [x] PrefixExpressionStatement
	- [x] PrefixExpression ;

- [ ] SimpleStatement
	- [ ] AssertStatement
	- [ ] SwitchStatement
	- [ ] DoStatement
	- [ ] BreakStatement
	- [ ] ContinueStatement
	- [ ] ReturnStatement
	- [ ] SynchronizedStatement
	- [ ] ThrowStatement
	- [ ] TryStatement
	- [ ] YieldStatement
	- [ ] IfStatement
	- [ ] WhileStatement
	- [ ] ForStatement

- [ ] IfStatement
	- [ ] IfThenStatement
	- [ ] IfThenElseStatement

- [ ] LocalClassOrInterfaceDeclaration:
	- [ ] ClassDeclaration
	- [ ] NormalInterfaceDeclaration

- [ ] StatementStartingWithName:
	- [ ] ExpressionStatement
	- [ ] LabeledStatement
	- [ ] LocalVariableDeclarationStatement

- [ ] LocalVariableDeclarationStatement:
	- [ ] LocalVariableDeclaration ;

- [ ] LocalVariableDeclaration:
	- [ ] {VariableModifier} LocalVariableType VariableDeclaratorList

- [ ] StatementNoShortIf:
	- [ ] StatementWithoutTrailingSubstatement
	- [ ] LabeledStatementNoShortIf
	- [ ] IfThenElseStatementNoShortIf
	- [ ] WhileStatementNoShortIf
	- [ ] ForStatementNoShortIf

- [ ] ExpressionStatement: 
	- [ ] StatementExpression ;

- [ ] StatementExpression:
	- [ ] Assignment
	- [ ] PostIncrementExpression
	- [ ] PostDecrementExpression
	- [ ] MethodInvocation
	- [ ] ClassInstanceCreationExpression

- [ ] PrefixExpression
	- [ ] PreIncrementExpression
	- [ ] PreDecrementExpression

- [x] Assignment:
	- [x] LeftHandSide AssignmentOperator Expression

- [x] LeftHandSide: 
	- [x] ExpressionName
	- [x] FieldAccess
	- [x] ArrayAccess 

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
	- [x] ConditionalOrExpression ? Expression : LambdaExpression

- [x] ConditionalOrExpression: 
	- [x] ConditionalAndExpression 
	- [x] ConditionalOrExpression || ConditionalAndExpression

- [x] ConditionalAndExpression: 
	- [x] InclusiveOrExpression 
	- [x] ConditionalAndExpression && InclusiveOrExpression

- [x] InclusiveOrExpression: 
	- [x] ExclusiveOrExpression
	- [ ] InclusiveOrExpression | ExclusiveOrExpression

- [ ] ExclusiveOrExpression:
	- [ ] AndExpression
	- [ ] ExclusiveOrExpression ^ AndExpression
 
- [ ] AndExpression:
	- [ ] EqualityExpression 
	- [ ] AndExpression & EqualityExpression
 
- [ ] EqualityExpression:
	- [ ] RelationalExpression
	- [ ] EqualityExpression == RelationalExpression
	- [ ] EqualityExpression != RelationalExpression

- [ ] RelationalExpression:
	- [ ] ShiftExpression
	- [ ] RelationalExpression < ShiftExpression
	- [ ] RelationalExpression > ShiftExpression
	- [ ] RelationalExpression <= ShiftExpression
	- [ ] RelationalExpression >= ShiftExpression
	- [ ] InstanceofExpression 

- [ ] InstanceofExpression: 
	- [ ] RelationalExpression instanceof ReferenceType
	- [ ] RelationalExpression instanceof Pattern

- [ ] ShiftExpression: 
	- [ ] AdditiveExpression 
	- [ ] ShiftExpression << AdditiveExpression
	- [ ] ShiftExpression >> AdditiveExpression
	- [ ] ShiftExpression >>> AdditiveExpression

- [ ] AdditiveExpression:
	- [ ] MultiplicativeExpression 
	- [ ] AdditiveExpression + MultiplicativeExpression
	- [ ] AdditiveExpression - MultiplicativeExpression

- [ ] MultiplicativeExpression:
	- [ ] UnaryExpression
	- [ ] MultiplicativeExpression * UnaryExpression
	- [ ] MultiplicativeExpression / UnaryExpression
	- [ ] MultiplicativeExpression % UnaryExpression

- [ ] UnaryExpression:
	- [ ] PreIncrementExpression 
	- [ ] PreDecrementExpression 
	- [ ] \+ UnaryExpression 
	- [ ] \- UnaryExpression 
	- [ ] UnaryExpressionNotPlusMinus 

- [ ] PreIncrementExpression: 
	- [ ] ++ UnaryExpression 

- [ ] PreDecrementExpression:
	- [ ] -- UnaryExpression 

- [ ] UnaryExpressionNotPlusMinus: 
	- [ ] PostfixExpression 
	- [ ] ~ UnaryExpression 
	- [ ] ! UnaryExpression 
	- [ ] CastExpression
	- [ ] SwitchExpression

- [ ] PostfixExpression: 
	- [ ] Primary
	- [ ] ExpressionName
	- [ ] PostIncrementExpression
	- [ ] PostDecrementExpression
- [ ] ExpressionName: 
	- [ ] Identifier 
	- [ ] AmbiguousName . Identifier
- [ ] PostIncrementExpression: 
	- [ ] PostfixExpression ++

- [ ] PostDecrementExpression:
	- [ ] PostfixExpression --

- [ ] Primary:
	- [ ] PrimaryNoNewArray
	- [ ] ArrayCreationExpression

- [ ] PrimaryNoNewArray: 
	- [ ] Literal
	- [ ] ClassLiteral
	- [ ] this
	- [ ] TypeName . this 
	- [ ] ( Expression )
	- [ ] ClassInstanceCreationExpression
	- [ ] FieldAccess
	- [ ] ArrayAccess
	- [ ] MethodInvocation
	- [ ] MethodReference

# Types
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
	- [ ] Identifier { . Identifier }

- [ ] PackageName: 
	- [ ] Identifier { . Identifier }

- [ ] TypeName: 
	- [ ] { Identifier . } TypeIdentifier

- [ ] PackageOrTypeName: 
	- [ ] Identifier { . Identifier }

- [ ] ExpressionName: 
	- [ ] Identifier { . Identifier }

- [ ] MethodName: 
	- [ ] Identifier 
		- [ ] but not yield

- [ ] AmbiguousName: 
	- [ ] Identifier { . Identifier }

- [ ] TypeIdentifier:
	- [ ] Identifier 
		- [ ] but not permits, record, sealed, var, or yield

- [ ] UnqualifiedMethodIdentifier: 
	- [ ] Identifier 
		- [ ] but not yield

#### Things that can start with a name
- In a class body declaration:
	- Class member declaration (field, method, nested class/interface)
- In block Statment:
	- Local variable declaration:
		- sequence of identifiers,
			- possibly with annotations and type parameters mixed in, 
			- then possibly Dims (`[`])
		- then identifier
			- possibly with Dims (`[`])
		- then possibly `=` or `,`
		- or `;`
	- Statement:
		- ExpressionStatement
			- Assignment
				- ExpressionName
					- sequence of identifiers then `=`
				- FieldAccess
					- primary `.` identifier
					- super `.` identifier
					- sequence of identifiers `.` super `.` identifier
				- ArrayAccess
			- PostIncrementExpression
			- PostDecrementExpression
			- MethodInvocation
			- ClassInstanceCreationExpression
		- LabeledStatement  
			- plain identifier, then `:`
		- LabeledStatementNoShortIf
				- plain identifier, then `:`


All statements that can start with an identifier will originate from here:

- [x] StatementStartingWithName:
	- [x] StatementExpression ;
	- [x] LabeledStatement
	- [x] LocalVariableDeclarationStatement


- [ ] StatementExpression:
	- [ ] Assignment
		- [ ] Identifier {. Identifier} = 
		- [ ] Primary . Identifier = 
		- [ ] super . Identifier = 
		- [ ] TypeName . super . Identifier = 
		- [ ] Identifier { . Identifier } \[ Expression \] = 
		- [ ] PrimaryNoNewArray \[ Expression \] = 
		- [ ] ArrayCreationExpressionWithInitializer \[ Expression \] =
	- [ ] PostIncrementExpression
		- [ ] Identifier {. Identifier} ++
		- [ ] primary ++
	- [ ] PostDecrementExpression
		- [ ] Identifier {. Identifier} --
		- [ ] primary --
	- [ ] MethodInvocation
		- [ ] Identifier { . Identifier } ( \[ArgumentList\] )
		- [ ] { Identifier . } TypeIdentifier . \[TypeArguments\] Identifier ( \[ArgumentList\] )
		- [ ] ExpressionName . \[TypeArguments\] Identifier ( \[ArgumentList\] )
		- [ ] Primary . \[TypeArguments\] Identifier ( \[ArgumentList\] )
		- [ ] super . \[TypeArguments\] Identifier ( \[ArgumentList\] )
		- [ ] { Identifier . } TypeIdentifier . super . \[TypeArguments\] Identifier ( \[ArgumentList\] )
	- [ ] ClassInstanceCreationExpression
		- [ ] new ...
		- [ ] Identifier { . Identifier } . UnqualifiedClassInstanceCreationExpression
		- [ ] Primary . UnqualifiedClassInstanceCreationExpression

- [ ] UnmodifiedLocalVariableDeclarationStatement:
	- [ ] LocalVariableType VariableDeclaratorList ;

- [ ] LabeledStatement:
	- [ ] identifier : Statement

- [ ] Assignment:
	- [ ] LeftHandSide AssignmentOperator Expression

- [ ] LeftHandSide: 
	- [ ] Identifier {. Identifier}
	- [ ] FieldAccess
	- [ ] ArrayAccess 

FieldAccess:
	Primary . Identifier
	super . Identifier
	TypeName . super . Identifier

ArrayAccess:
	Identifier { . Identifier } \[ Expression \]
	PrimaryNoNewArray \[ Expression \]
	ArrayCreationExpressionWithInitializer \[ Expression \]

MethodInvocation:
	Identifier { . Identifier } ( \[ArgumentList\] )
	{ Identifier . } TypeIdentifier . \[TypeArguments\] Identifier ( \[ArgumentList\] )
	ExpressionName . \[TypeArguments\] Identifier ( \[ArgumentList\] )
	Primary . \[TypeArguments\] Identifier ( \[ArgumentList\] )
	super . \[TypeArguments\] Identifier ( \[ArgumentList\] )
	{ Identifier . } TypeIdentifier . super . \[TypeArguments\] Identifier ( \[ArgumentList\] )

LocalVariableType:
	UnannType
	var

ClassInstanceCreationExpression:
		UnqualifiedClassInstanceCreationExpression
		ExpressionName . UnqualifiedClassInstanceCreationExpression
		Primary . UnqualifiedClassInstanceCreationExpression

---

- [ ] StatementStartingWithName:
	- [ ] LocalVariableDeclarationStatement
	- [ ] Assignment
		- [ ] Identifier {. Identifier} = 
		- [ ] Primary . Identifier = 
		- [ ] super . Identifier = 
		- [ ] TypeName . super . Identifier = 
		- [ ] Identifier { . Identifier } \[ Expression \] = 
		- [ ] PrimaryNoNewArray \[ Expression \] = 
		- [ ] ArrayCreationExpressionWithInitializer \[ Expression \] =
	- [ ] PostIncrementExpression
		- [ ] Identifier {. Identifier} ++
		- [ ] primary ++
	- [ ] PostDecrementExpression
		- [ ] Identifier {. Identifier} --
		- [ ] primary --
	- [ ] MethodInvocation
		- [ ] Identifier { . Identifier } ( \[ArgumentList\] )
		- [ ] { Identifier . } TypeIdentifier . \[TypeArguments\] Identifier ( \[ArgumentList\] )
		- [ ] ExpressionName . \[TypeArguments\] Identifier ( \[ArgumentList\] )
		- [ ] Primary . \[TypeArguments\] Identifier ( \[ArgumentList\] )
		- [ ] super . \[TypeArguments\] Identifier ( \[ArgumentList\] )
		- [ ] { Identifier . } TypeIdentifier . super . \[TypeArguments\] Identifier ( \[ArgumentList\] )
	- [ ] ClassInstanceCreationExpression
		- [ ] new ...
		- [ ] Identifier { . Identifier } . new
		- [ ] Primary . new
	- [x] LabeledStatement:
		- [x] identifier : Statement
	- [ ] UnmodifiedLocalVariableDeclarationStatement:
		- [ ] LocalVariableType VariableDeclaratorList ;

Out of these, what is the lowest precedence?
	Assignment, as it contains the others on the left side, but others cannot directly contain it.
	Therefore factoring out `term = right` is probably simplest

- [ ] Assignment:
	- [ ] term = right

- [ ] term:
	- [ ] Identifier {. Identifier}
	- [ ] Primary . Identifier
	- [ ] super . Identifier 
	- [ ] TypeName . super . Identifier
	- [ ] Identifier { . Identifier } \[ Expression \]
	- [ ] PrimaryNoNewArray \[ Expression \]
	- [ ] ArrayCreationExpressionWithInitializer \[ Expression \]

Now let's see what this covers.
`LabeledStatement` clearly becomes:
- [ ] LabeledStatement:
	- [ ] term : Statement
		- [ ] term must be an identifier expression


```
term:
	ExpressionTerm
	TypeTerm
	
ExpressionTerm:
	term1 [AssignOp ExpressionTerm]

term1:
	term2 [ ? Expression : term1]
	
term2:
	term3 []
```


- [ ] Expression:
	- [ ] LambdaExpression
	- [ ] ConditionalExpression
	- [ ] Assignment

	