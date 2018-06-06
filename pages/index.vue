<template>

  <el-main>
    <el-collapse v-model="activeNames"
                 @change="handleChange">
      <el-collapse-item title="Preprocessing "
                        name="1">
        <div>(include, define)</div>
      </el-collapse-item>
      <el-collapse-item title="run control "
                        name="2">
        <div> (integrator, tinit, dt, nsteps, init-step, comm-mode, nstcomm, comm-grps)</div>
      </el-collapse-item>
      <el-collapse-item title="langevin dynamics "
                        name="3">
        <div> (bd-fric, ld-seed)</div>

      </el-collapse-item>
      <el-collapse-item title="energy minimization"
                        name="4">
        <div> (emtol, emstep, nstcgsteep)</div>
      </el-collapse-item>
      <el-collapse-item title="shell molecular dynamics"
                        name="5">
        <div>(emtol,niter,fcstep) </div>
      </el-collapse-item>
      <el-collapse-item title="test particle insertion(rtpi) "
                        name="6">
        <div>properties</div>
      </el-collapse-item>
      <el-collapse-item title="output control"
                        name="7">
        <div>(nstxout, nstvout, nstfout, nstlog, nstcalcenergy, nstenergy, nstxout-compressed, compressed-x-precision, compressed-x-grps, energygrps</div>
      </el-collapse-item>
      <el-collapse-item title="neighbor searching"
                        name="8">
        <div>(cutoff-scheme, nstlist, nstcalclr, ns-type, pbc, periodic-molecules, verlet-buffer-tolerance, rlist, rlistlong) </div>
      </el-collapse-item>
      <el-collapse-item title="electrostatics "
                        name="9">
        <div>(coulombtype, coulomb-modifier, rcoulomb-switch, rcoulomb, epsilon-r, epsilon-rf) </div>
      </el-collapse-item>
      <el-collapse-item title="VdW"
                        name="10">
        <div>(vdwtype, vdw-modifier, rvdw-switch, rvdw, DispCorr) </div>
      </el-collapse-item>
      <el-collapse-item title="tables"
                        name="11">
        <div>(table-extension, energygrp-table)</div>
      </el-collapse-item>
      <el-collapse-item title="Ewald"
                        name="12">
        <div>(fourierspacing, fourier-nx, fourier-ny, fourier-nz, pme-order, ewald-rtol, ewald-geometry, epsilon-surface) </div>
      </el-collapse-item>
      <el-collapse-item title="Temperature coupling"
                        name="13">
        <div>(tcoupl, nsttcouple, tc-grps, tau-t, ref-t) </div>
      </el-collapse-item>
      <el-collapse-item title="Pressure coupling"
                        name="14">
        <div>(pcoupl, pcoupltype, nstpcouple, tau-p, compressibility, ref-p, refcoord-scaling) </div>
      </el-collapse-item>
      <el-collapse-item title="simulated annealing "
                        name="15">
        <div>(annealing, annealing-npoints, annealing-time, annealing-temp)</div>
      </el-collapse-item>
      <el-collapse-item title="velocity generation"
                        name="16">
        <div>(gen-vel, gen-temp, gen-seed) </div>
      </el-collapse-item>
      <el-collapse-item title="bonds"
                        name="17">
        <div>(constraints, constraint-algorithm, continuation, shake-tol, lincs-order, lincs-iter, lincs-warnangle, morse) </div>
      </el-collapse-item>
      <el-collapse-item title="Energy group exclusions"
                        name="18">
        <div>(energygrp-excl) </div>
      </el-collapse-item>
      <el-collapse-item title="Walls"
                        name="19">
        <div>(nwall, wall-type, wall-r-linpot, wall-atomtype, wall-density, wall-ewald-zfac) </div>
      </el-collapse-item>
      <el-collapse-item title="COM pulling"
                        name="20">
        <div>(pull, ...) </div>
      </el-collapse-item>
      <el-collapse-item title="NMR refinement"
                        name="21">
        <div>(disre, disre-weighting, disre-mixed, disre-fc, disre-tau, nstdisreout, orire, orire-fc, orire-tau, orire-fitgrp, nstorireout) </div>
      </el-collapse-item>
      <el-collapse-item title="Free energy calculations"
                        name="22">
        <div>(free-energy, nstdhdl, dhdl-print-energy, init-lambda, delta-lambda, fep-lambdas, coul-lambdas, vdw-lambdas, bonded-lambdas, restraint-lambdas, mass-lambdas, temperature-lambdas, sc-alpha, sc-coul, sc-power, sc-r-power, sc-sigma, couple-moltype, couple-lambda0, couple-lambda1, couple-intramol) </div>
      </el-collapse-item>
      <el-collapse-item title="Expanded ensemble simulation"
                        name="23">
        <div>(lmc-stats, lmc-mc-move, lmc-seed, lmc-gibbsdelta, mc-temperature, nst-transition-matrix, init-lambda-weights, initial-wl-delta, wl-scale, wl-ratio, symmetrized-transition-matrix, lmc-forced-nstart, mininum-var-min, lmc-weights-equil, weight-equil-wl-delta, weight-equil-number-all-lambda, weight-equil-number-steps, weight-equil-number-samples, weight-equil-count-ratio, simulated-tempering, simulated-tempering-scaling, sim-temp-low, sim-temp-high) </div>
      </el-collapse-item>
      <el-collapse-item title="Non-equilibrium MD"
                        name="24">
        <div>(acc-grps, accelerate, freezegrps, freezedim, cos-acceleration, deform) </div>
      </el-collapse-item>
      <el-collapse-item title="Electric fields"
                        name="25">
        <div>(E-x, E-xt, E-y, E-yt, E-z, E-zt ) </div>
      </el-collapse-item>
      <el-collapse-item title="Mixed quantum/classical dynamics"
                        name="26">
        <div>(QMMM, QMMM-grps, QMMMscheme, QMmethod, QMbasis, QMcharge, Qmmult, CASorbitals, CASelectrons, SH) </div>
      </el-collapse-item>
      <el-collapse-item title="Implicit solvent"
                        name="27">
        <div>(implicit-solvent, gb-algorithm, nstgbradii, rgbradii, gb-epsilon-solvent, gb-saltconc, gb-obc-alpha, gb-obc-beta, gb-obc-gamma, gb-dielectric-offset, sa-algorithm, sa-surface-tension) </div>
      </el-collapse-item>
      <el-collapse-item title="AdResS settings"
                        name="28">
        <div>pro(adress, adress_type, adress_const_wf, adress_ex_width, adress_hy_width, adress_ex_forcecap, adress_interface_correction, adress_site, adress_reference_coords, adress_tf_grp_names, adress_cg_grp_names) </div>
      </el-collapse-item>
      <el-collapse-item title="User defined thingies"
                        name="29">
        <div>(user1-grps, user2-grps, userint1, userint2, userint3, userint4, userreal1, userreal2, userreal3, userreal4) </div>
      </el-collapse-item>

    </el-collapse>

  </el-main>

</template>

<script>
  export default {
    data() {
      return {
        activeNames: ['1']
      };
    },
    methods: {
      handleChange(val) {
        console.log(val);
      }
    }
  }

</script>

<style scoped>
.el-main {
  background-color: #e9eef3;
  /* height: 100vh; */
  color: #333;
  text-align: center;
  line-height: 160px;
}

body > .el-container {
  margin-bottom: 40px;
}

.el-container:nth-child(5) .el-aside,
.el-container:nth-child(6) .el-aside {
  line-height: 260px;
}

.el-container:nth-child(7) .el-aside {
  line-height: 320px;
}
</style>
