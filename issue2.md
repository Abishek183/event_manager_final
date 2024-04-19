# issue2 : User Role ANONYMOUS

## FIX:
The default user role 'anonymous' is not an accepted entry into the DB. It was fixed by modifying the default user role to 'user' in the user_model.py
>>> role: Mapped[UserRole] = Column(SQLAlchemyEnum(UserRole), default=UserRole.USER, nullable=False)