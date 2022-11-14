En este video hemos agregado un nuevo componente signup

Tambien hemos definido en auth actions (public/src/app/auth/state/auth.actions.ts):

export const SIGNUP_START = '[auth page] signup start';
export const SIGNUP_SUCCESS = '[auth page] signup success';

export const signupStart = createAction(
  SIGNUP_START,
  props<{ email: string; password: string }>()
);

export const signupSuccess = createAction(
  SIGNUP_SUCCESS,
  props<{ user: User }>()
);

Por ultimo y no menos importante, ha sido necesario cambiar el orden de las rutas definidas en public/src/app/auth/auth.module.ts
de:

{ path: '**', redirectTo: 'login' }
{ path: 'login', component: LoginComponent },
{ path: 'signup', component: SignupComponent }

a:

{ path: 'login', component: LoginComponent },
{ path: 'signup', component: SignupComponent },
{ path: '**', redirectTo: 'login' }