# profile_picture_url not getting updated

## Cause:
The variable is created as string attribute during database creation. But when updating the value to the database we are passing the value as url instead of string. Its resulting in type mismatch.

## Fix:
The type from URL is changes to string and the issue is resolved.
>>> profile_picture_url: Optional[str] = Field(
        None,
        description="An updated URL to the user's profile picture.",
        example="https://example.com/profile_pictures/john_doe_updated.jpg"
    )