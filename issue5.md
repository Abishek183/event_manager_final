# 500 error in user creation

## cause:
There was no validation done and error set when trying to create user with already existing email id.

## Fix:
Validation for email id is added and corresponding error message is set.
>>> existing_email = await UserService.get_by_email(db, user.email)
    if existing_email:
        raise HTTPException(status_code=status.HTTP_400_BAD_REQUEST, detail="Email ID already exists")