# dln-go

Cuvva's library to generate, parse, and validate GB DVLA issued driving licenses.

## Usage

### `Generate`

```go
userDetails := dln.UserDetails{
    PersonalName: "Charles",
    FamilyName: "Bbaee",
    Sex: "M",
    BirthDate: "1975-07-01",
}

dln, err := dln.Generate(userDetails, true)
if err != nil { /* do something */ }

// DLN = BBAEE707015C9
```

### `Validate`

```go
dln := "BBAEE707015C99WY"
userDetails := dln.UserDetails{
    PersonalName: "Charles",
    FamilyName: "Bbaee",
    Sex: "M",
    BirthDate: "1975-07-01",
}

isValid, err := dln.Validate(dln, userDetails, true)
if err != nil { /* do something */ }

// isValid = true
```

### `Parse`

```go
dln := "BBAEE707015C99WY"

userDetails, err := dln.Parse(dln, true)
if err != nil { /* do something */ }

/*
userDetails := dln.UserDetails{
    PersonalName: "C",
    FamilyName: "Bbaee",
    Sex: "M",
    BirthDate: "1975-07-01",
}
*/
```
